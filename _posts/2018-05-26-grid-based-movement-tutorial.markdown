---
layout: single
author_profile: false
classes: 
    - wide-left
title:  "Grid Based Movement"
date:   2018-05-26
related: true
category: 
    - Tutorials
    - Godot
tag:
    - 2D
    - Beginners
comments: true
toc: true
---

This is a Grid Based Movement tutorial it will be created into a video soon enough.
Hope you guys like it.

Grid-Based systems are common in retro and many newer indie games in this post we will go through creating a script that does just that and then we will try to understand the steps involved in it.

## Requirements For This Tutorial

As of writing this tutorial I don't expect any previous knowledge of Godot or Programming or Maths. Probably basic maths. Nothing above middle school.

## Who is this tutorial for:

Anyone who wants to learn to code the more experienced can also get a few take-aways. So it is for people with lesser programming or Godot experience than a probably intermediate level user. 

## Project Files

Download the project files from my github repository.

Not uploaded yet. Will be uploaded with the video tutorial.


## Grid-Based Movement

For this we will be using of a lerp function, to move the player by directly modifying the value of position.

### Understanding Grid

In a grid each block is fixed distance from the ones adjacent/having a side common to it, if not atleast it follows a pattern which makes movement in a grid pridictable.

So each movement to left is a movement by `x`.

![Grid Image](https://i.imgur.com/OuXQcI7.png)

And in a grid the most common movement is 4 way over the regular 8 way movement. And in case of analog stick the movement can even be infinite but here we are not going to be using analog.

### Script or Code
<hr/>

```swift
extends Node2D

# using export makes it possible to edit the variable in the inspector
export(float) var speed = 10.0     
export(int) var tileSize = 32    

# store target and initial position to move to and from.
var target = Vector2()
var initial = Vector2()

# store the input from arrow keys to allow movement
var inp = Vector2()

# stores time that is incremented by delta
var d = 0 


func _process(delta):
    var val = d * speed
    # use the val to move from initial to final position
    if val >= 1.0: 
        val = 1
        d = 0
    # set the position equal to the lerp between initial and target position
    self.position.x = lerp(initial.x, target.x, val)
    self.position.y = lerp(initial.y, target.y, val)
    # check and see if the input is zero
    if inp.magnitude != 0:
        # setup initial and target position using tileSize and inp
        initial = self.position
        # using "self." is not necessary just for better readability
        target = initial + tileSize * inp
        # reset inp = (0,0)
        inp = Vector2()
    elif self.position == target:
        # if input is zero and target is reached start taking inputs again
        get_input_dir()
    else:
        # as delta is time from last from so if you keep adding it will reach
        # 1 when the total time elapsed is 1 second. So it is just time in secs.
        d += delta

func get_input_dir():
    # this check allows for only 4-way motion,
    if inp.x == 0:
        # convert boolean to int to use them to get the input direction
        inp.y = (int(Input.is_action_pressed("ui_down"))
                                    - int(Input.is_action_pressed("ui_up")))
    if inp.y == 0:
        # convert boolean to int to use them to get the input direction
        inp.x = (int(Input.is_action_pressed("ui_right"))
                                  - int(Input.is_action_pressed("ui_left")))
```


### Explaination
<hr/>

The code is quite simple, we use the value of initial position and target position set when Input is non-zero and target position is equal to our current position in world.

In the code target position is the position on the grid that we have to move created using the tileSize that you input.

You see that I use a fourth variable `d` to store time which when equal to or greater than 1 will be reset to 0. That means 1 second divided by speed will be the time in which the movement is complete which allows for creating movement as per real world time. 

And helps the person modifying the setting understand how to use the code better.
That means if, `speed = 0.5` then the time taken for the movement will be 2 seconds and if `speed = 2` then the time taken fot the movement will be half a second.

You can even use different tileSizes for x and y axis but that is not required. This will allow you to create grids with rectangles rather than squares, it's silly but possible. It can be implemented like,
```swift
export(Vector2) var tileSize;
// skipping..... to the point
target = initial + Vector2(tileSize.x * inp.x, tileSize.y * inp.y)
```
Then we check and see if the target is reached then we can again take input and start moving. Voila!

And my last trick is simple really but if you are a beginner at programming try to understand and put your explaination in the comments section. It will help you understand code from more advanced levels to try to think more.
I will message you the right answer or tell you if you are write will be fun.

And if you are more advanced and you have problems understanding the code. Then seriously put something in the comments we need to talk.

## Conclusion

In the end we realize that it was quite simple to create grid-based movement and even simpler to modify it upto our needs from a square to rectangle. And also with 8 direction motion implementation., that follows the grid.

The tutorial will be uploaded once the newer input strength features are available in an alpha build atleast until then this is the best and most reliable way. 

If you have any problems or want to share feedback or just have any questions you feel like asking use the comments section below.

<embed src="https://swarnimarun.github.io/test-repo" height="600" width="1024">
