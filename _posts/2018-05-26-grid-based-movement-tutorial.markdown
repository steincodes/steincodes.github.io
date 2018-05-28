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

As of writing this tutorial I don't expect any previous knowledge of Godot or Programming or Maths.

## Who is this tutorial for:

Anyone who wants to learn to code the more experienced can also get a few take-aways.

## Project Files

Download the project files from my github repository.
Link: [godot-beginners-tutorials][godot-beginners-tutorials] Not uploaded yet. Will be uploaded with the video tutorial.

[godot-beginners-tutorials]: https://github.com/swarnimarun

## Grid-Based Movement

For this we will be using of a lerp function, to move the player by directly modifying the value of position.

### Understanding Grid

In a grid each block is fixed distance from the ones adjacent/having a side common to it, if not atleast it follows a pattern which makes movement in a grid pridictable.

So each movement to left is a movement by `x`.

![Grid Image Player](https://i.imgur.com/ioluyQ1.jpg)

And in a grid the most common movement is 4 way over the regular 8 way movement. And in case of analog stick the movement can even be infinite but here we are not going to be using analog.

### Script or Code
<hr/>

```swift
extends Node2D

# using export makes it possible to edit the variable in the inspector
export(float) var speed = 10.0     
export(int) var tileSize = 32    

var target = Vector2()
var initial = Vector2()
var inp = Vector2()

func _process(delta):
    # set the position equal to the lerp between initial and target position
    self.position = lerp(initial, target, speed * delta)
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

func get_input_dir():
    # this check allows for only 4-way motion,
    #                  if you want 8 way motion then remove the ifs
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

You can even use different tileSizes for x and y axis but that is not required. It can be implemented like,
```swift
export(Vector2) var tileSize;
// skipping..... to the point
target = initial + Vector2(tileSize.x * inp.x, tileSize.y * inp.y)
```
Then we check and see if the target is reached then we can again take input and start moving. Voila!

But finally, we use the int() conversion of the bools to get the axis strength i.e. if the left and right both keys are pressed then the answer should be zero and if one of them is pressed it should be 1 with the respective sign.


## Conclusion

In the end we realize that it was quite simple to create grid-based movement and even simpler to modify it upto our needs from a square to rectangle. And also with 8 direction motion implementation., that follows the grid.

The tutorial will be uploaded once the newer input strength features are available in an alpha build atleast until then this is the best and most reliable way. 

If you have any problems or want to share feedback or just have any questions you feel like asking use the comments section below.
