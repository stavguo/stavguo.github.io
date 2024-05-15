+++
title = 'Gravity Grab'
categories = [ "Projects" ]
tags = [ "game-development" ]
date = 2021-03-03T00:00:00-05:00
draft = false
image = 'cover.png'
[[links]]
title = "Gravity Grab"
description = 'Click here to play Unity WebBuild.'
website = 'http://www-personal.umich.edu/~dmellogu/portfolio/GravityGrabWebBuild/'
image = 'cover.png'
+++

For my first solo game development project, I created a third-person puzzle-action game called Gravity Grab. The goal of the game is to navigate a group of astronauts through hazardous levels. I was inspired by Pikmin, and I also wanted to use Unity's advanced physics articulations. The core mechanic the player must utilize is to physically connect the astronauts to each other. In order to do this, I used a collision-detection method using HashSets to organize clumps of adjacent astronauts. As for gameplay, I wanted to find a balance where the astronauts feel expendable yet valued by the player since they function as important resources for solving puzzles. Gravity Grab makes heavy use of the publish-subscribe architecture pattern in order to increase component-reusage.