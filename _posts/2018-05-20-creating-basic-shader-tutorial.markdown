---
layout: single
classes: wide
title:  "Basics of Shaders with Godot"
date:   2018-05-20
related: true
category: 
    - Tutorials
tag:
    - Godot
    - Shaders
    - Beginners
comments: true
---
Creating shaders is something that all programmers should be familiar with if they want to code games for themselves.

Godot is a powerful game engine and Godot's Shading language as of the time of writing this tutorial uses OpenGL GLES 3.0 for rendering, which is likely going to be ported to Vulkan in the near future.

So, Godot's Shading language is quite similar to OpenGL while still having lots of differences.

### Requirements For This Tutorial

As of writing this tutorial I don't expect any previous knowledge of Godot or Programming or Shaders. But I expect that the reader knows basic Maths cause I won't be explaining it.

### Who is this tutorial for:

If you are a programmer with no knowledge of Shaders or Graphics Programming or if you are a designer/artist you is looking to learn to add more umph! to their games you are Welcome.

### Project Files

Download the project files from my github repository.
Link: [godot-shader-tutorials][shader-repo]

[shader-repo]: https://github.com/swarnimarun

## Understanding Graphics Programming

So the first step to becoming a programmer is to learn the basics of what you are doing and similar is the case with Graphics Programming.

![Alt Text for image](../../images/teaser.png)

To give you all a basic idea, let's compare the GPU to a factory or a plant that processes lots of stuff at tremendous speeds and this makes the job of managing very difficult. In a similar fashion GPU's process image information and the management of it all is done through shaders.

Shaders are the managers of GPU while GPU's cores are the workers.

In case of GPUs all the workers are unaware of the other worker's work and so it becomes difficult to coordinate. So shaders devise ways to help with it.

This all boils down and tells us that shaders simply use the GPU with all it's limitations to produce the final result.

And just like there are multiple managers for managing work at different levels in a factory, there are multiple shaders for processing the images. Like vertex shader, fragment shader and light shaders being some of the most basic examples.

You also have the ability of adding more managers to make the job easier but that's gonna cost you, no not money but processing power.

If you find that you still don't understand the logic of shaders then you should go ahead, and read [The Book Of Shaders](https://thebookofshaders.com/), it is an amazing resource that will help you understand the basics of the shaders.

## Getting into Shaders in Godot 3.0

So finally we start the attack on the Godot Shaders.

Godot Shaders use GLES but a custom version that is built for Godot. So I must say that it makes quite a few things relatively easier and also breaks most of the connections with base OpenGL. So doing a copy-paste of code isn't an option.

Godot docs tell us that all shaders must have a `shader_type` and this can either `canvas_item, spatial or particles`.
Next up we should also add a `render_mode` and this can have various options based on the `shader_type` and our needs.