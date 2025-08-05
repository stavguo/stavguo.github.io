+++
title = 'Bouncing DVD Logo Demo in Go'
date = 2025-08-05T08:14:59-04:00
draft = false
image = 'cover.png'
[[links]]
title = "Ebitengine"
description = 'A dead simple 2D game engine for Go'
website = 'https://ebitengine.org/'
[[links]]
title = "A Tour of Go"
description = 'The tour covers the most important features of the language'
website = 'https://go.dev/tour/list'
[[links]]
title = "Ark"
description = 'Ark is an archetype-based Entity Component System (ECS) for Go'
website = 'https://github.com/mlange-42/ark'
+++

<div class="iframe-container">
    <iframe 
        src="https://gustavo.zip/go-dvd-logo/" 
        width="716" 
        height="581" 
        frameborder="0" 
        scrolling="no"
        style="
            border: none; 
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
        ">
    </iframe>
</div>

<style>
.iframe-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin: 20px 0;
}

.iframe-container iframe {
    width: 716px;
    height: 581px;
    max-width: 100%;
}

@media (max-width: 756px) {
    .iframe-container iframe {
        width: calc(100vw - 40px);
        height: calc((100vw - 40px) * 581 / 716);
    }
}

@media (max-width: 480px) {
    .iframe-container iframe {
        width: calc(100vw - 20px);
        height: calc((100vw - 20px) * 581 / 716);
        border-radius: 10px;
    }
}
</style>

After a few months with PICO-8 and Lua, I grew to appreciate the simplicity of its independent `update()` and `draw()` loop. However, I also found myself constrained by the fantasy console's limitations—a 64kb OS, a language prone to off-by-one errors, and a sparse package ecosystem. For example, while most modern languages have several Entity Component System (ECS) libraries to choose from, PICO-8 has just [one](https://github.com/jesstelford/pecs). I wanted to find a framework that offered the same creative freedom without the technical constraints.

My search led me to [Ebitengine](https://ebitengine.org/), a game engine for Go, which I discovered through a [GameFromScratch](https://www.youtube.com/c/gamefromscratch) video. Having been interested in learning Go or Rust, I decided to dive in. I completed the [Tour of Go](https://go.dev/tour/list) in my spare time and was immediately hooked.

While Go isn't the most common choice for game development, its strengths in backend systems, concurrency, and performance are highly relevant to my interests. The language introduces features that feel like a breath of fresh air. For instance, formatting is standardized with a single command: `gofmt -w .`. This is a welcome change from the world of JavaScript, where I constantly wrestled with competing linters and style configs. Go's package system also encourages clean project organization from the start. In the past, I'd often create a monolithic `main` file with a messy `src` directory. While using an ECS architecture provides some structure, Go's packages make it intuitive to group related logic into clean, separate modules.

This bouncing DVD logo demo, while simple on the surface, is intentionally over-engineered to serve as a template and learning exercise. I implemented a scene manager using Go's `interface`s, defining `Update`, `Draw`, `Enter`, and `Exit` methods to handle game states and resource management. Integrating libraries is also a breeze. For the ECS, I used [Ark](https://github.com/mlange-42/ark), a flexible library designed for high-performance simulations. A key feature I appreciate is the ability to run queries outside of systems, which is a limitation I found in other libraries like `bitecs`. This allows for a more flexible, event-driven approach without managing state flags every frame.

The result is a clean, organized project structure that feels scalable. I can navigate the file hierarchy without feeling overwhelmed, and the combination of Go and Ebitengine gives me the confidence to tackle more ambitious projects, from a massive game to a small weekend game jam tool.

I hope this write-up proves useful to others exploring game development in Go.