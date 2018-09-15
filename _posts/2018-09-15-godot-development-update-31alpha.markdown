---
layout: single
header:
    image: "https://github.com/steincodes/steincodes.github.io/raw/master/images/godot_31_alpha_v2.png"
toc: true
title:  "Godot Development Update 3.1 Alpha is HERE!"
date:   2018-09-15 
related: true
category: 
    - News
    - Godot
tag:
    - Development
comments: true
---

So it's been a while since I did one of these, but I had to wait for Godot 3.1 for more features to talk about and this will likely be followed by a series of video and text posts for each of the new features of Godot. 

I might even do some feature fixing while I am at it, but exams are closing in so no promises.


OK, so we now have the Godot 3.1 Alpha with us and we have now reached the state of feature freeze for this new version.
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">After months of work on our upcoming 3.1 version, we&#39;ve now reached the alpha milestone and publish a first official snapshot of <a href="https://twitter.com/hashtag/GodotEngine?src=hash&amp;ref_src=twsrc%5Etfw">#GodotEngine</a>&#39;s master branch.<br><br>Happy testing and bug hunting! 🐞 <a href="https://twitter.com/hashtag/FOSS?src=hash&amp;ref_src=twsrc%5Etfw">#FOSS</a><a href="https://t.co/emVHojnC7j">https://t.co/emVHojnC7j</a></p>&mdash; Rémi Verschelde (@Akien) <a href="https://twitter.com/Akien/status/1035427197702610944?ref_src=twsrc%5Etfw">August 31, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


In this I will cover all the notable changes, and also some of the new and notable ones.*This list is in NO way shape or form exhaustive.*
Also you all should remember that 50% os these aren't properly complete yet and none are bug free. Also if I am being honest I won't be using 3.1 in production unless these are fixed.

But that doesn't mean that we can't be hyped for it. And use it in it's current state.
Here's a link to download the nightly builds. 
I have my own compiled version of Godot that seems to be working flawlessly which I will link at the end.

## NEW Animation Features

We have got a some very welcome new Animation features with the introduction of revamp of the Animation Player and the new Animation Graph.

### Animation Player
![](https://godotengine.org/storage/app/uploads/public/5b1/962/d39/5b1962d39ad28606691486.png)
Animation Player was always the silver lining for Godot being how simple and easy it was to use, but now with the new changes it's soo much more powerful and godotific.
Ok that last word was on my list of words to use this year.

But seriously we have some pretty interesting changes this time to the Animation Player. Like,
- Revamped Multiple tracks
- Bezier Curves
- Audio Waveform drawing
- Copy and Paste
- and more....

Read more at [this link](https://godotengine.org/article/godot-gets-brand-new-animation-editor-cinematic-support).

### AnimationGraph/AnimationTree
![](https://godotengine.org/storage/app/uploads/public/5b3/2c4/a01/5b32c4a01b3dc233539052.gif)
We also saw Reduz write a whole new AnimationTree with state management and blends and a lot of awesome things, which was also then refactor/revamped. I am still unsure about it's completion.

Read More about it [here](https://godotengine.org/article/godot-gets-new-animation-tree-state-machine).

## NEW Visual Shader Editor
![](https://godotengine.org/storage/app/uploads/public/5b4/a6c/003/5b4a6c0038ced706516053.gif)
So we finally have our long awaited, Visual Shader Editor. But is it perfect, nope. Is it the best Visual Shader Editor? nope. Is it the new Awesome thing? nope.

....Does it work? yes. And we are only in alpha, hope to see lots of changes to it to make it better and more productive tool.

Read more [here](https://godotengine.org/article/visual-shader-editor-back).

## Constructive Solid Geometry Features
![](https://godotengine.org/storage/app/media/csg/csg7.gif)
CSG is a big thing for quick prototyping in 3D, and has lots of advantages. But the biggest one is that you won't have to fire up a 3D suite to make minor changes to simple geometry to add doors and hallways.

Godot's implementation is more special as it allows for in-game use as well, you could theoritically use the nodes to create sort of procedural geometry.

Read more [here](https://godotengine.org/article/godot-gets-csg-support).

## Input Strength System
Inputs in Godot's are ususally termed as Actions and it's a feature of Godot that was always very nice but never complete until now that is.

This new Strength system will allow for the player to move in accordance with the amount of the turn provided to the joysticks on the controllers. Which is a pretty basic but an essential feature which was missing until now.

Read more [here](https://godotengine.org/article/handling-axis-godot).

## OpenGL ES 2 Backend Closing Completion
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">New progress report! More lighting code and shadow mapping!<a href="https://t.co/flRiJD7ILG">https://t.co/flRiJD7ILG</a></p>&mdash; Thomas Herzog (@karroffel) <a href="https://twitter.com/karroffel/status/1021324392352108545?ref_src=twsrc%5Etfw">July 23, 2018</a></blockquote>

We now also have a partially complete ES 2.0 Backend in place which means better mobile support, support for WebGL 1.0 and hopefully the ability to run HTML5 games on Chrome properly as well.

As of now many 3D features are missing and lots of bugs and issues are present but we can hope to see it complete before 3.1 official release.

Read more [here](https://godotengine.org/article/gles2-and-gdnative-progress-report-7).

## Typed GDScript [Optional Typing]
![](https://godotengine.org/storage/app/uploads/public/5b1/f4f/b2f/5b1f4fb2f023a968578982.png)

Typed GDScript is finally inside of Godot, even thought added as an optional feature, but this still makes the GDScript language that much more awesome to use. And especially improves the code completion. Now ain't that awesome.

Read more [here](https://godotengine.org/article/optional-typing-gdscript).

## 2D Meshes and 2D Skeletons
![](https://godotengine.org/storage/app/media/skeleton2d/bonetut19.gif)

2D Meshes are now there in Godot and also 2D Skeletons, so we might finally be able to move forward Spine and DragonBones, or will we?

Read [this issue](https://github.com/godotengine/godot/issues/20601) for more understanding on why this feature is still not useful enough for our needs.

Read more [here](https://godotengine.org/article/godot-gets-2d-skeletal-deform).

## IK and SoftBodies
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Yet more amazing work by <a href="https://twitter.com/_AndreaCatania?ref_src=twsrc%5Etfw">@_AndreaCatania</a>, Adding soft body and cloth support to Godot!<a href="https://t.co/hxTP5SEugT">https://t.co/hxTP5SEugT</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1026893544068403200?ref_src=twsrc%5Etfw">August 7, 2018</a></blockquote>

I think these are features that most engines try to sell a lot so here's my pitch.

IK or Inverse Kinematics is now in Godot so try it out create perfect reload animations and use Softbodies for those awesome Capes, in your next Superman Game.

Read more about IK [here](https://godotengine.org/article/skeleton-inverse-kinematic) and about Softbodies [here](https://godotengine.org/article/soft-body).

## NEW Inspector
![](https://godotengine.org/storage/app/media/inspector/inspector3.png)
![](https://godotengine.org/storage/app/media/inspector/inspector4.png)

The new Inspector bring in a ton of changes to the UI/UX of the engine which have tried to make the engine more modern and also added to the customizability of the code.

Read more [here](https://godotengine.org/article/godot-gets-new-inspector).

## NEW Tileset Editor
Finally we got a Tileset Editor as part of the core Godot Engine that looks awesome, but still is ridden with bugs, but don't let that get you down it will surely be better by the official release phase. And try it out already and make some issues to keep track of those untracked bugs in this awesome new tool.

Read more [here](https://github.com/godotengine/godot/pull/20585).

## Animated Textures
This is a not so notable feature but this is important as it makes a lot of things much easier in Godot especially the part with Animating the Tiles in a tileset, now isn't that great.

In this feature we see a addition of a new type of Resource called Animated Texture that can be used instead of the everyday texture to provide animated effects, you can specify fps and frames using this resource.


## Conclusion

With all this new feature list hope you don't get overwhelmed, nah. As far I know you guys won't be overwhelmed.
You can hope to see more posts like this to add more this list of features that is still largely incomplete for reasons like time constraints and all.

And as an overview I can surely say that Godot Engine is it's fun to see it improve like this. Hope we get to Godot 4 soon. :)

Hope you guys find time to mention your favourite features down in the comments