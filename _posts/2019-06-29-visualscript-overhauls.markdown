---
layout: single
title:  "Visual Scripting System overhaul!"
date:   2019-06-29 
related: true
category: 
    - News
    - Godot
tag:
    - Development
    - VisualScript
comments: true
---

This is a changelog and manual of all the changes made to the VisualScript system of sorts. This should help you all understand the changes before you all dive in and start trying the builds already.

*These changes are part of my long list of changes planned and in work for Godot VisualScript System under GSOC.*

The builds are at [google docs folder link](https://drive.google.com/drive/folders/1jZxsxn7dwdsrYXBollUFuHgE6wiWtW3T?usp=sharing)
They will be regularly updated.

Quick Video of the changes in action: 

<iframe width="640" height="360" src="https://drive.google.com/file/d/1V1o5sHzvDDs1i8dgtRYwerx2juUFxsk7/preview" frameborder="0" allowfullscreen></iframe>

## Let's start with the first change that's the unification of the Visual Script Graph.
This means that all functions are now in the same view no need for tapping around to reach them.

These changes also include the changing of the nodes figuring out the function they are part of being connected to other nodes. This is supposed to be implicit(it should feel natural) and if you have any problems with not properly being able to handle connections between nodes, be sure to go to [this Pull Request](https://github.com/godotengine/godot/pull/29681) and notify me or just put it in the comments section here.

This included refactoring of all the Visual Script Editor code to take into account this change which ended up kinda big.
![gify](https://user-images.githubusercontent.com/19930870/59534439-f1768780-8f0b-11e9-9030-1adebc6541e6.gif)

Next up are a few minor changes were with UI the gifs should be enough but it's mostly about quick function creation, more expressive search and the node connection swapping.

![](https://user-images.githubusercontent.com/19930870/59723009-d7f27a00-9242-11e9-92b8-36409c35e0b9.gif)

<hr/>

![](https://user-images.githubusercontent.com/19930870/59982236-a60b5a00-962c-11e9-9091-571e156fed6b.gif)

The latest feature of automatic type conversions or what I like to call Type Sense is still kind of WIP so this makes inter type node connection a little bit of a hassle but you can use NIL types to get over it.. Hopefully I will fix it in a day(by the time most people read this so go ahead with the builds without any worries).
![vs-type-sense](https://user-images.githubusercontent.com/19930870/60389045-528b8700-9ad8-11e9-9695-d52f21f04099.gif)

**Some BUGS as of now:**

![vs-type-sense-2](https://user-images.githubusercontent.com/19930870/60389047-5c14ef00-9ad8-11e9-8a6f-bb2b7d406317.gif)

List of known problems:
- Undos sometimes can be a little confusing(eg: you have to undo twice for port swapping).
- Quick Function Creation don't work properly with non-sequence nodes
- The position of Constructor Nodes can be a little problematic.

**There maybe other bugs I don't know of yet, so be sure to point them out in the pull request if you find them.**

This is the list of changes as of 29/06/2019. (Things here are subject to change and suggestions are welcome in the Pull Request that has been created)

- Suggestions at [pull request for visual script changes](https://github.com/godotengine/godot/pull/29681).

- Builds to try and test things out [google drive folder with Windows and Linux builds](https://drive.google.com/drive/folders/1jZxsxn7dwdsrYXBollUFuHgE6wiWtW3T?usp=sharing).
