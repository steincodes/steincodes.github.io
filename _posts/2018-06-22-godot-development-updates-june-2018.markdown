---
layout: single
header:
    image: "https://i.ytimg.com/vi/exRHbVC0hHA/maxresdefault.jpg"   
toc: true
title:  "Godot Development Update June 2018"
date:   2018-06-22 
related: true
category: 
    - News
    - Godot
tag:
    - Development
comments: true
---

This is a continuation to the Godot Development Update series, I will also be including some active proposal/discussion links that will allow you all to share your ideas. Although this depends on when you are reading this post.

I will make a video as soon as some more features get merged.


## Typed GDScript

Finally Typed GDScript has a PR, it's a little old now. But I have tested the repo myself, builds and runs fine some problems here and there but it's WIP so it's expected.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">GDScript completion refactor is coming along nicely. <a href="https://twitter.com/hashtag/godotengine?src=hash&amp;ref_src=twsrc%5Etfw">#godotengine</a> <a href="https://t.co/VuFooxLBGu">pic.twitter.com/VuFooxLBGu</a></p>&mdash; George Marques (@vnen) <a href="https://twitter.com/vnen/status/1009632816458592257?ref_src=twsrc%5Etfw">June 21, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

[Godot PR Link: Typed GDScript](https://github.com/godotengine/godot/pull/19264)
 , this a huge dicussion but the main idea is Typed GDScript is on it's way.


## Reduz has completed work on AnimationPlayer and new AnimationGraph Node

AnimationGraph is the new version of the redundant AnimationTreePlayer.
It has features like Blends and better UI/UX to help improve the workflow it's really awesome.

And AnimationPlayer has all the changes that you might or might not have imagined and it's all awesome.

### Tweets by reduz on the topic

#### AnimationPlayer

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">New animation workflow progress, more handy in general and works better for transform and call tracks. Old workflow is still there of course. <a href="https://t.co/xk4jOE0FhY">pic.twitter.com/xk4jOE0FhY</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1000880370504650752?ref_src=twsrc%5Etfw">May 27, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr">Same for call track.. <a href="https://t.co/S6PRrSoJwi">pic.twitter.com/S6PRrSoJwi</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1000880372895412226?ref_src=twsrc%5Etfw">May 27, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Sprite frames are now easier to animate... <a href="https://t.co/QwaBEZOcb9">pic.twitter.com/QwaBEZOcb9</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1001800966830743553?ref_src=twsrc%5Etfw">May 30, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Visualizing sub-animations and audio tracks is possible now, so it&#39;s much easier to do cinematic style editing. Will still eventually add a special type of audio track where you can drag resources to it, edit built-in volume, etc. <a href="https://t.co/XKlDthB4cB">pic.twitter.com/XKlDthB4cB</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1001851585771732992?ref_src=twsrc%5Etfw">May 30, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Almost done with Bezier curve editor, turned out to be pretty nice... <a href="https://t.co/2eM0Ri4ci2">pic.twitter.com/2eM0Ri4ci2</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1003362472722649089?ref_src=twsrc%5Etfw">June 3, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">While this used to work before, it now makes a lot more sense that selected nodes are marked in the track list, as before tracks could be all over the place: <a href="https://t.co/9uPgmHsdci">pic.twitter.com/9uPgmHsdci</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1003696152351473669?ref_src=twsrc%5Etfw">June 4, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Another feature in the popular demand list, tack copying and pasting (between animations too): <a href="https://t.co/uDwQc8zX7M">pic.twitter.com/uDwQc8zX7M</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1003972281851371521?ref_src=twsrc%5Etfw">June 5, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Audio previews now generate smoothly in a thread, like in DAWs. Thanks, past life as an audio programmer... <a href="https://t.co/c2NtbJvvG5">pic.twitter.com/c2NtbJvvG5</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1004114553150550016?ref_src=twsrc%5Etfw">June 5, 2018</a></blockquote>

#### AnimationGraphPlayer

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Tirelessly working on the new AnimationGraphPlayer, which supersedes the old and rusty AnimationTreePlayer. Will support state machine, recursive blend trees, blend spaces, color on active connections, and custom scripted nodes for blending. Hope to have it working this week... <a href="https://t.co/st6hwj0squ">pic.twitter.com/st6hwj0squ</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1008141626701762560?ref_src=twsrc%5Etfw">June 17, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">pretty feedback all over the place.. <a href="https://t.co/QbHiCqcfbm">pic.twitter.com/QbHiCqcfbm</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1008821624928337922?ref_src=twsrc%5Etfw">June 18, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Blend spaces are now fully working :) <a href="https://t.co/Q3mPRaXoIv">pic.twitter.com/Q3mPRaXoIv</a></p>&mdash; Juan Linietsky (@reduzio) <a href="https://twitter.com/reduzio/status/1009867874071085057?ref_src=twsrc%5Etfw">June 21, 2018</a></blockquote>


## Godot Jam 2018 - June

Godot had a huge Game Jam this year if you weren't a part of it don't worry it will happen again in few months.

Go ahead and start rating games on itch.io page of the Jam now. We have 111 entries all awesome stuff.
[Jam Link on itch.io](https://itch.io/jam/godotjam062018)

Also go ahead and checkout my game and rate it, My Game: [Tempors](https://itch.io/jam/godotjam062018/rate/270340)
, as a heads up you should remember that Chrome doesn't work properly with Godot games. So use FireFox instead.


## Nvidia Flex Update by Andrea Catania

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Here another <a href="https://twitter.com/hashtag/nvidia?src=hash&amp;ref_src=twsrc%5Etfw">#nvidia</a> <a href="https://twitter.com/hashtag/flex?src=hash&amp;ref_src=twsrc%5Etfw">#flex</a> implementation update in <a href="https://twitter.com/hashtag/GodotEngine?src=hash&amp;ref_src=twsrc%5Etfw">#GodotEngine</a>  <a href="https://t.co/1oA9NXoa8T">https://t.co/1oA9NXoa8T</a> now is possible to use Primitive shape, check the video</p>&mdash; Andrea Catania (@_AndreaCatania) <a href="https://twitter.com/_AndreaCatania/status/1006098930550091776?ref_src=twsrc%5Etfw">June 11, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">This is 3th update about <a href="https://twitter.com/hashtag/nvidia_flex?src=hash&amp;ref_src=twsrc%5Etfw">#nvidia_flex</a> implementation in <a href="https://twitter.com/hashtag/godotengine?src=hash&amp;ref_src=twsrc%5Etfw">#godotengine</a> here you can see mesh deformation according to clusters transformation of body: <a href="https://t.co/xy0N2uw5mu">https://t.co/xy0N2uw5mu</a></p>&mdash; Andrea Catania (@_AndreaCatania) <a href="https://twitter.com/_AndreaCatania/status/1008994183380701185?ref_src=twsrc%5Etfw">June 19, 2018</a></blockquote>

I think the tweet says enough here.


## Problems with preventing "engine bloat" and the AssetLibrary

This discussion is active and you all should quickly go there and check out the new features and changes being proposed. Probably also mention some ideas, although make sure to read other answers before replying so as to not create duplicates, and remember the netiquttes.

### Summary Of the Discussions
The discussion is about whether we should remove some features and make Godot more compact or should we consider bloating up the engine a little.
The problem here lies in the views not in the approach so if you want to add something read a bit more first.

[Issue Link: Engine Bloat Discussion](https://github.com/godotengine/godot/issues/19486)
 , I think the new sub-system idea was too good to pass up on but I am not the voice of the world check it out yourself.


## My Tileset creation process improvement suggestion --Active

In this proposal by yours-truly I point out how easy it will be to add some easier-tileset generation System.
This one hasn't been discussed much but I am working on it in my free time, I have been suggested some separate ideas so will be a while before I make anything public on my work.

[Godot Issue Link: Tileset creation process improvement](https://github.com/godotengine/godot/issues/19538)
 , The Discussion is still on-going. 


## Conclusion

So this sums up the list and I will update this post until the end of June 2018, so you can follow it until then.

Godot is really a wonderful engine and I hope you all like the way it's developing if you have some feedback for the engine or this site/post put them in the comments section. I will try to address them.
