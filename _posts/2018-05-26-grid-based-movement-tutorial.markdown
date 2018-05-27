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

Grid-Based systems are common in retro and many newer indie games in this post I have 2 different methods of implementing grid-based movement each having various advantages and disadvantages. I will also list the uses of the two methods.

## Requirements For This Tutorial

As of writing this tutorial I don't expect any previous knowledge of Godot or Programming or Maths.

## Who is this tutorial for:

Anyone who wants to learn to code the more experienced can also get a few take-aways.

## Project Files

Download the project files from my github repository.
Link: [godot-beginners-tutorials][godot-beginners-tutorials]

[godot-beginners-tutorials]: https://github.com/swarnimarun

## Method #1

The first method is using of a lerp function, to move the player by directly modifying the value of position.

### Pros

- It's super simple to implement.
- It uses just the basic method so easy to manage.

### Cons

- Limited and difficult to modify.

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

You can even use different tileSizes for x and y axis but that is not required.
