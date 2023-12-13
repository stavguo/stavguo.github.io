+++
title = 'Phaser-Emblem: Grid-Based Movement over Procedurally Generated Terrain'
categories = [ "Projects" ]
date = 2022-10-28T00:00:00-05:00
draft = false
image = 'cover.png'
[[links]]
title = 'Phaser Emblem'
website = 'https://github.com/stavguo/phaser-emblem'
+++

I created a browser game inspired by Nintendo’s Fire-Emblem franchise using the ECS (Entity Component System) pattern. I used [Phaser]('https://phaser.io/'), a desktop and mobile HTML5 game framework, coupled with the [bitECS]('https://github.com/NateTheGreatt/bitECS') library. Using TypeScript, I adapted Sebastian Lague's [pathfinding algorithm]('https://github.com/SebLague/Pathfinding') in C#. My favorite part of this project was altering the A* pathfinding algorithm to optimally traverse terrain with variable movement costs. For instance, an entity can move further through grassy plains on one turn versus moving through thick forests. Potential tiles an entity can travel to in one turn appear as tinted tiles when an entity is selected.