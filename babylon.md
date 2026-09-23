---
layout: page
title: Babylon
---


# Babylon.js

## Editor Choices

### Babylon Editor

You can work with or without [the editor](https://editor.babylonjs.com/download)

> **NOTE:** You may need to install [node.js](https://playground.babylonjs.com/) — a javascript runtime environment

### VSCode

If you prefer, you should be able to view the results of your code in VSCode. You may end up editing TypeScript — or you could conceivably wrap your Babylon.js in HTML and edit it as a web page (this is the first approach I'll try. Let you know how it goes and how to do it, if working)

### Playground

There is also a [Babylon Playground](https://playground.babylonjs.com/) where you can try things out

## My Production Preference

I'm going to develop in [an HTML page](arenaRoids01.html), at least until I decide I need to change. But I think the scope of my _arena sphere asteroids_ game (I'm calling it ArenaRoids until I get a better name!) lends itself well to a single page of Javascript nested in HTML. 

> **EMAILED:** To each of you, [a zip file](arenaRoids01.html.zip) which you can unzip, open in [VSCode](https://code.visualstudio.com/) and preview with the new [Integrated Browser](https://code.visualstudio.com/docs/debugtest/integrated-browser)

This page includes three code libraries, the Babylon CORE, loaders for various 3D model types and GUI stuff like crosshair tageting etc. It should be enough for our purposes, but here's a more complete list of possible includes:

CORE\
`<script src="https://cdn.babylonjs.com/babylon.js"></script>`

MATERIALS LIBRARY\
`<script src="https://cdn.babylonjs.com/materialsLibrary/babylonjs.materials.min.js"></script>`

LOADERS: glTF, GLB, OBJ, STL, etc.\
`<script src="https://cdn.babylonjs.com/loaders/babylonjs.loaders.min.js"></script>`

POST-PROCESSES\
`<script src="https://cdn.babylonjs.com/postProcessesLibrary/babylonjs.postProcess.min.js"></script>`

PROCEDURAL TEXTURES\
`<script src="https://cdn.babylonjs.com/proceduralTexturesLibrary/babylonjs.proceduralTextures.min.js"></script>`

SERIALIZERS\
`<script src="https://cdn.babylonjs.com/serializers/babylonjs.serializers.min.js"></script>`

GUI\
`<script src="https://cdn.babylonjs.com/gui/babylon.gui.min.js"></script>`

INSPECTOR\
`<script src="https://cdn.babylonjs.com/inspector/babylon.inspector.bundle.js"></script>`

VIEWER\
`<script src="https://cdn.babylonjs.com/viewer/babylon.viewer.js"></script>`

> **NOTE:** Babylon officially says these CDN URLs are intended for learning and small experiments, not production deployment. For a class project and GitHub Pages exercises, they're very convenient; for a finished public application, Babylon recommends the ES6 @babylonjs/core packages instead.


## Example Code

I tried this prompt:

```
I'm creating a game in Babylon.js, running on the web. I've included src urls for the Core, Loaders and GUI. 
I want to create a dark blue sphere 100 meters in diameter with my POV at the center, I should be able to turn in any direction using mouse position. 
Near the perimeter, within the sphere, I want to randomly generate smaller spheres called asteroids, radii randomized between 0.5 meters and 2.5 meters (always appearing within the sphere but at a distance from it greater than their radius) moving in randomized directions and initially slow randomized speeds. (Create a discreet "speed" variable to be randomized so I can change it in the code to my liking). 
Asteroids should collide with and rebound from each other, as well as the inner surface of the sphere, but the sphere should add a small, randomized increment to the speed of each asteroid. (Create another discreet "inc" variable to randomize and add this increment, so I can also edit this in the code.

> Write this html page to to your permitted folder autonomousSite. Name the file arenaRoids.html
```
And I got [this code](arenaRoids.zip)
