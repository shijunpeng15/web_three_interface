# Introduction
This repo contains webGL Three.js based interface demos for interactions with 3d data using mouse and touch

# 01 mouse hover on mesh

[Live demo](https://homesmartmesh.github.io/web_three_interface/01_mesh_mouse_on_hover/)

[01 mouse hover on mesh - github directory](./01_mesh_mouse_on_hover)

## Gif Demo

<img src="./01_mesh_mouse_on_hover/media/demo.gif" width="600">

The user moves the mouse over the sphere object which changes color on enter and on exit events.

## Design

<img src="./01_mesh_mouse_on_hover/media/design.png" width="600">

This mouse hover example is easily reusable as it is split in modules. The "three_mouse.js" contains the conversion logic from the web mouse events to the 3D mouse mesh events. It is isolated from the main application logic in "main.js", and both isolated from the "three_app.js" which contains clasical three environment and shapes creation.
* On init : The user is only supposed to know the names of the created obejcts in the the three scene, and passes a list of names to get back a list of meshes with `three.getObjects()`.
  
  This list is then provided to the "three_mouse.js" module.
* On event, the "three_mouse.js" triggers events on mouse entering the mesh and exit from the mesh. These events provide the name of the mesh. The name can be used to call a "three_app.js" function that sets the state according to the event, in this demo the emissive color is changing.

# 02 mouse down and touch

[Live demo](https://homesmartmesh.github.io/web_three_interface/02_mouse_down_and_touch/)

[02 mouse down and touch - github directory](./02_mouse_down_and_touch)

## Gif Demo

<img src="./02_mouse_down_and_touch/media/demo.gif" width="600">

The design and the on-hover effect from demo 01 are kept. Added is a "mouse down" and "touch start" events. These new events act on the specular effect of the material to give a green shininess.

Note that on the gif, the mouse down event is shown with a yellow spot added by the gif recorder. When the user touches the screen and start moving the scene, the mouse disappears and the touch is visible through the touch gray spot.
