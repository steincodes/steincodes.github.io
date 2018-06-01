---
layout: single
header:
    image: "https://i.ytimg.com/vi/exRHbVC0hHA/maxresdefault.jpg"   
toc: true
title:  "Godot Development Update May 2018"
date:   2018-05-27 
related: true
category: 
    - News
    - Godot
tag:
    - Development
comments: true
---

I have been following Godot quite closely for some-time now but I realized that most people aren't really aware of all this so here is list of the most important updates I have come across.
I will also be including some active proposal/discussion links that will allow you all to share your ideas. Although this depends on when you are reading this post.

Here's a video if you like videos(it's can't be updated so new links will be added as pinned comments),
<iframe width="560" height="315" src="https://www.youtube.com/embed/exRHbVC0hHA" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br/>

## Android Exporter Proposal

In this proposal by @reduz(Juan Linietsky) it was discussed and decided that proposal to re-write the current Export System to a better more User-Freindly one will be accepted.

Here's the proposal, 
> Do away entirely with the current export system and make the UI build the APK every time exporting is requiered by calilng gradle. Allow installing extensions from UI (or asset library) for ADMob and other stuff with almost no effort.

It was clearly a land-slide. But now the bad news.
This feature will liely not become a part of Godot 3.1. For it's not being implemented by any developers as of writing this post but let's hope that it soon gets one.

[Godot Issue Link: Future Of Android Exporter](https://github.com/godotengine/godot/issues/18865)
 , The Discussion is still on-going. 

## Godot 3.1 Alpha Likely to Come By July 1st

So in another discussion is was more or less confirmed that Godot 3.1 Alpha will be there by July 1st. As many of the major features have been completed and others are in heavy development.

Here's a list,
- Completed
    - 2D Meshes, 2D Skeletons, CSG and new Inspector -- @reduz
    - Physical Bones                                 -- @AndreaCatania
    - Input Strength System                          -- @groud
    - GDNative C++ API Network                       -- @karrofel
- Incomplete and in-development
    - OpenGL ES2 backend                             -- @karrofel
    - Typed GDScript                                 -- @vnen
    - New AnimationPlayer, Animation Tree Editor and Visual Shader Editor  -- @reduz
    - IK and softbodies                              -- @AndreaCatania
    - Editor Theme Improvements                      -- @djrm
    - C# Export System                               -- @neikeq

[Godot Issue Link: Aiming For July 1st for Godot 3.1 Alpha](https://github.com/godotengine/godot/issues/19101)
 , there will be surely other features that are not mentioned here cause they skipped my mind or just weren't so big.


## Godot Might get a Texture Painter

Next is the update that is not confirmed but is still fascinating enough to make into this list. 
That @bauxitedev created a Proof-Of-Concept of a texture Painter in Godot which was received quite well by the devs so it might weasley it's way into the Godot Game Engine.

Even @karrofel(The OpenGl 2.0 backend dev) contributed to the repo to help fix a problem.
So fingers crossed.

Here's a demo video,
<iframe width="560" height="315" src="https://www.youtube.com/embed/nbG_XAxmIlA" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br/>
[Link to the repo: godot-texture-painter](https://github.com/Bauxitedev/godot-texture-painter)
 , even though it's quite early to say anything for sure but a texture painter might just be what Godot needs to be better than other engines. And I am not pointing at the engine that you might think.

## New Addon-System Proposal -- Active

This discussion is active and you all should quickly go there and check out the new features and changes being proposed. Probably also mention some ideas, although make sure to read other answers before replying so as to not create duplicates, and remember the netiquttes.

### Summary Of the Discussions
The discussion is about wheter we should change to a package manager with dependencies or should be change to a new sub-project system that would enable more flexibilty. 

[Issue Link: New Addon System](https://github.com/godotengine/godot/issues/19178)
 , I think the new sub-system idea was too good to pass up on but I am not the voice of the world check it out yourself.

## My UI Improvements Suggestions -- Active

This one is there to try to change something that cause alot of problems in the Godot UI. 

So basically this is made to address the issues with the Godot that really cause all of us annoyance so check it out and give your thoughts on the flow of things.

[Issue Link: UI Improvements Suggestions](https://github.com/godotengine/godot/issues/19197)
 , there are lots of problems with the current Godot UI and you might want everything to be fixed but please understand somethings need time and some just can't be done so if the devs say no then it's most likely a no especially if the dev is @reduz.
 
## Update: Blender might soon have default support for Godot

Awesome news. Blender will be implementing support for external Game Engines. Godot will likely be added. Here's some proof.

![Tweet Reply Image](https://i.imgur.com/5pIc3rS.png)

Link: [Blender's Official Tweet](https://twitter.com/blender_org/status/1001110824012967936)

## Conclusion

So this sums up the list and I will update this post until the end of May 2018, so you can follow it until then.

Godot is really a wonderful engine and I hope you all like the way it's developing if you have some feedback for the engine or this site/post put them in the comments section. I will try to address them.
