+++
title = 'Creating "Swash" for the 12th Brackeys Game Jam'
date = 2024-09-24T18:22:16-04:00
draft = false
image = 'cover.png'
categories = [ 'Projects' ]
tags = [ 'game-development', 'game-jams' ]
+++

The theme for the 12th Brackeys Game Jam was ‘the calm before the storm.’ My entry, Swash, is a memory-based, top-down action game featuring a sandpiper searching for food.

## Concept and Inspiration

My initial thought was to create a game about a tsunami or tidal wave. However, I wanted my game to stand out by interpreting the theme in a unique way. I didn't want to incorporate a literal storm, but I did want to retain the two phases of being in a storm and not. My idea evolved by scaling down the concept, focusing instead on how to gamify normal waves breaking on a beach. The end product was heavily inspired by one of my favorite Pixar short films, "Piper," where a young sandpiper learns to find invertebrates hidden in the sand by observing the incoming water. In **Swash**, players can move in and out of the water freely but can only dig for food when the water is down (the calm before the storm). The twist is that players can only see where the food is when the water rises (the storm), requiring them to memorize the positions of the food. This mechanic creates a tense yet rewarding experience, capturing the essence of the "calm before the storm."

## Implementing Low-Discrepancy Sampling

To distribute the food in a way that felt natural and challenging, I implemented a **low-discrepancy sampling technique**. This method ensures that the food is spread out evenly but unpredictably, creating a balanced gameplay experience. Low-discrepancy sequences, such as the Halton sequence, are particularly useful in game development for generating points that cover an area uniformly without clustering. I used the "Subrandom" method from [this awesome blog post](https://blog.demofox.org/2017/05/29/when-random-numbers-are-too-random-low-discrepancy-sequences/) that visualizes different sampling techniques.

## Animating the Waves

Animating the waves was another critical aspect of creating an immersive experience. I experimented with various animation curves and ultimately found that an **ease in/out quadratic curve** provided the most realistic wave motion. This curve allowed the waves to accelerate smoothly as they approached the shore and decelerate as they receded, mimicking the natural ebb and flow of tides. You can checkout visualizations and implementations of many animation curves in [this pico-8 forum post](https://www.lexaloffle.com/bbs/?tid=40577).

## Conclusion

Participating in the Brackeys Game Jam was a fun opportunity to push my creative and technical boundaries. By leveraging low-discrepancy sampling and fine-tuning animation curves, I was able to create a unique and engaging game that I hope to revisit in the future. I think the game could use some other pesky birds, dogs scaring away prey, and obstacles such as rocks.
<iframe src="https://itch.io/embed/2973171" width="552" height="167" frameborder="0"><a href="https://stavguo.itch.io/swash">Swash by stavguo</a></iframe>