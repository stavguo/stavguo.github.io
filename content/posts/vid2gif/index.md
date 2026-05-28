---
title: "Building Vid2Gif: A Deep Dive into High-Performance Video Processing with Tauri and Svelte"
date: 2026-05-27
draft: false
tags: ["rust", "tauri", "svelte", "ffmpeg"]
image: 'frame_042.png'
---
Vid2Gif was born out of a personal frustration with the existing landscape of video-to-gif converters. While tools like Gifski and ezgif are excellent, they often force a trade-off between privacy (uploading files online) and precision (limited CLI control). By leveraging the Tauri framework with a SvelteKit frontend, I set out to build a cross-platform desktop application that brings professional-grade GIF generation—powered by FFmpeg and Gifski—into a localized, high-performance GUI. The goal was simple but ambitious: create an all-in-one package that handles any video format, offers frame-accurate trimming, and exposes fine-grained quality settings without ever letting your data leave your machine.

One of the most significant backend hurdles was implementing a video player that felt "desktop native" in its responsiveness. Standard file loading in a WebView is often sluggish for large video files, especially when scrubbing. To solve this, I moved away from simple file paths and implemented a custom `stream://` URI scheme protocol in Rust. This allowed me to manually handle HTTP Range requests, serving specific byte chunks directly from the filesystem to the frontend's HTML5 video element. This implementation enables near-instant seeking and smooth scrubbing through multi-gigabyte files, as the application only reads the exact packets required for the current frame rather than attempting to buffer the entire stream. You can find more information on using this method with tauri in this helpful [blog post](https://liyuan.org/posts/projects/tauri-video-fail/).

On the frontend, the complexity lay in managing the spatial logic of the workspace. Creating a tool that allows users to both trim and crop video meant dealing with a constant flux of aspect ratios. I spent a significant amount of time perfecting the logic to "stretch" and scale different video sizes within a variety of window dimensions without introducing letterboxing or UI breakage. To ensure the precision required for high-quality GIFs, I bypassed the standard (and often lazy) `timeupdate` event in favor of a `requestAnimationFrame` loop in Svelte. This watchdog runs 60 times a second, allowing for frame-accurate looping between markers and a perfectly synchronized preview, ensuring that the GIF you see in the app is exactly what you get in the final export.

You can check out the project on github [here](https://github.com/stavguo/vid2gif) and the latest release [here](https://github.com/stavguo/vid2gif/releases).

![Gif of Vid2Gif usage](usage.gif)