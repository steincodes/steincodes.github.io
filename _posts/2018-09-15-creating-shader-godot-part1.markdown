---
layout: single
header:
    image: "https://github.com/steincodes/steincodes.github.io/raw/master/images/Thumbnail_Shader_Coding.png"
toc: true
title:  "Coding Shaders in Godot Part-1"
classes:
    - wide-left
author_profile: false
date:   2018-09-15
related: true
category: 
    - Tutorials
    - Godot
tag:
    - Shaders
    - Beginners
comments: true
---
Creating shaders is something that all programmers should be familiar with if they want to code games for themselves.

Godot is a powerful game engine and Godot's Shading language as of the time of writing this tutorial uses OpenGL GLES 3.0 for rendering, which is likely going to be ported to Vulkan in the near future.

So, Godot's Shading language is quite similar to OpenGL while still having lots of differences.

For extra questions or long discussions about more tutorials and programming and design related stuff, join my discord, [Steincodes Server Invite](https://discord.gg/AqDfU3X). 

## Requirements For This Tutorial

As of writing this tutorial I don't expect any previous knowledge of Godot or Programming or Shaders. But I expect that the reader knows basic Maths cause I won't be explaining it. I will explain complex maths though.

Also the more you know the more you will learn from this likely, cause I think I will put all lot of info here.

## Who is this tutorial for:

If you are a programmer with no knowledge of Shaders or Graphics Programming or if you are a designer/artist you is looking to learn to add more umph! to their games you are Welcome.
Or you are a experinced person looking to learn Godot's shading language.

## Project Files

Download the project files from my github repository.
Link: [godot-shader-tutorials][shader-repo]

[shader-repo]: https://github.com/steincodes/godot-shader-tutorials

## Understanding Graphics Programming

So the first step to becoming a programmer is to learn the basics of what you are doing and similar is the case with Graphics Programming.

To give you all a basic idea, let's compare the GPU to a factory that processes lots of stuff at tremendous speeds and this makes the job of managing very difficult. In a similar fashion GPU's process image information and the management of it all is done through shaders.

Shaders are the managers of GPU while GPU's cores are the workers.
This also allows for parallel processing of information. Just as in factories multiple lines are working parallel to each other.

In factories workers don't know that's the serial number of the file last processed by his neighbour. Similarly, in case of GPUs all the cores are unaware of the other cores's process and so it becomes difficult to coordinate. This is a major drawback of parallel processing. 
And, so shaders devise ways to help with it.

This all boils down and tells us that shaders simply use the GPU with all it's limitations to produce the final result.

And just like there are multiple managers for managing work at different levels in a factory, there are multiple shaders for processing the images. Like vertex shader, fragment shader and light shaders being some of the most basic examples.

You also have the ability of adding more managers to make the job easier but that's gonna cost you, no not money but processing power.

If you find that you still don't understand the logic of shaders then you should go ahead, and read [The Book Of Shaders](https://thebookofshaders.com/), it is an amazing resource that will help you understand the basics of the shaders.

## Getting into Shaders in Godot 3

So finally we start the attack on the Godot Shaders.

Godot uses a custom shading language which is very much similar to OpenGL and this makes it easy to learn it from a experienced person's point of view but what about a beginner, how to learn it.

You can learn OpenGL and then transition to the Godot Shading language like I did, or just wait for someone to help you do it.

If you are like me and want to take the things in your own hands, open the [The Book Of Shaders](https://thebookofshaders.com/), learn the basics.
Next watch some OpenGL videos and learn just how exactly shaders work.
Also learn atleast some Linear Algebra and Matrix Maths.
Finally come back to Godot and start with the docs and some testing, and you should be able to do everything that you thought was meaningless before.


Now for the populus that wants to start small, and not bother with any OpenGL.
You are in luck we have a Visual Shader Editor now.(Parts of this was written before Visual Shader Editor existed).

**So now, you can just forget about everything else and not worry what shaders are?** *Wrong.*
Godot's shader editor is like a Visual Shader programming tool.

And I hate to say it but you can't use it without experience with actual shader programming.

So let's get accustomed to the basics.

1. Shader's are special programs that tell how to render some data on the screen. Simple.
2. Shader's work in parallel so are oblivous to the state of other instances of the code.
3. Shader's need to be divided into types like Vertex and Fragment and Light based on what they do. 
>- Vertex shader runs per vertex on screen
>- Fragment shader runs per fragment(likely a pixel) on the screen
>- Light shader runs to render light effect that are baked in after the first parts of the shader have been drawn.
4. Finally all this runs on the basis of drawing pixel on given positions so you can change what and how they draw it by changing/manupilation the data provided.

### So let's start with some code.......

```glsl

uniform float variable_name; // This is a variable that takes input 
// meaning it can be accessed from outside the shaders
// and is shared among the instances of the shader code,
// and can't be changed inside the shader code

// types you see in shaders go like this,
// float - floating point numeric data
// int - decimal numeric data
// bool - boolean
// sampler2D - this is the texture data
// uint - unsigned int i.e. no -ve's, 0 to 2^32 (that's kinda huge)
// and so on...

```
See the list at, [this link](http://docs.godotengine.org/en/3.0/tutorials/shading/shading_language.html#data-types).

```glsl

void vertex() {
    // this is the vertex shader function
}

void fragment() {
    // this is the fragment shader function
}

// for experienced shader programmers,
// what happens here is that code from each function is taken,
// parsed and put into specific shaders afer proper transpilation
// which is then compiled and the errors is/are thrown out
// which makes the life of a Godot shader programmer easier
// cause we all know how much pain goes into debugging opengl

```

```glsl

// in godot you have lots of things from opengl like
varying float variable; 
// this is used to send info from one step of process to next
// i.e. as we know fragment shaders are called after vertex so,
// we can use this type of keywords to send a value from vertex to fragment

// also it's good to remember that most of the GLSL ES 2.0+
// data types are supported in Godot
// like vec2, ivec2, bvec2, bool and so on...

```

```glsl

// before I forget in Godot we have lots of helper
// called render modes and they are taken from the
// shader_type context
// i.e. shader_types define what kind of a shader we have
// which simply selects the renderer for our code
// and gives us a context to look into like,

shader_type canvas_item; // uses 2D renderer
// and opens the door to variables and functions
// inside the canvas_item context

// NOTE * EACH SHADER MUST HAVE A shader_type
// render_modes are  optional

```

FOR the list of the render_modes and shader_types available use, [this link](http://docs.godotengine.org/en/3.0/tutorials/shading/shading_language.html#shader-types)

```glsl

// now back to uniforms
uniform float cutoff : hint_range(0,1);
// we can tell the godot editor to give the variable a range
// this adds a slider to the view helping with editing the property

// similarly we have
uniform sampler2D myTexture : hint_albedo;
// this tells godot to specify a default white color to the texture
```

```glsl

//Writing your first complete shader in Godot
// this simply multiplies the uniform color with the texture giving it a tint
shader_type canvas_item;
render_mode unshaded; // this turns all the editor shader effects off

uniform vec4 colorTint : hint_color; // input a color

void fragment() {
    // most of the times you will be using this function
    COLOR = texture(TEXTURE, UV);
    // COLOR is the "out vec4" variable of fragment method
    // out - variables are variables used to pass on values for processing
    // similar to a reference to a variable

    // texture method turns a sampler2D = TEXTURE using UV
    // into a vec4 value holding, r,g,b,a channels of color

    // UV and TEXTURE are "in" values in fragment method
    // like a const argument in C++
    // so you can't edit them but only read them
    // to edit UV do,
    // vec2 uv = UV;
    // edit uv here and then,
    // COLOR = texture(TEXTURE, uv); // and VOILA! haha

    // TEXTURE holds the original texture of the node the shader is on
    // like the sprite of the sprite node

    // and the UV is the position of the current fragment

    COLOR.rgb *= colorTint.rgb; // only use the colors not alpha
    // You can edit COLOR by,
    // COLOR.rgb = vec3(1); // this turns the color into white
    // you can use anything like COLOR.rg, COLOR.r, COLOR.rb and so on
    // and still refer to the respective vec values and then edit them

    // the fragment is rendered as per the COLOR value that goes out of this method
}

```

Now to do it in the Visual Shader Editor( more explaination will be added soon enough ).
For now just use this image, as reference.
![](https://github.com/steincodes/steincodes.github.io/raw/master/images/multiply_color_visual_shader.PNG)

For now that concludes the part one.
Next one we will code more things and also try Visual Shader Editor more.

## Conclusion

This is just the tip of the ice berg and there was no real programming here just a guide hope to create more programming focused articles in the near future.
Will also make articles on the performance of shaders and how to write more advanced shaders.

But before you leave please put your favorite shader resource in the comments to help the future readers of this article.