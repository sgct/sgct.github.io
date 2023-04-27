---
title: Configuration Files

has_children: true
has_toc: false
nav_order: 7
---

# General layout
The format for the SGCT configuration files is XML with a single [Cluster](cluster) tag that can contain 1 or more [Node](node) tags, a [User](user) tag, an optional [Settings](settings) tag, an optional [Capture](capture) tag, and an optional [Tracker](tracker) tag.  Each of the tags is described on this page further below.

# General layout (DRAFT)
The format for the SGCT configuration files is JSON that contains information about Nodes, Windows, Viewports, Projections, etc.
Below you'll find information about all tags and settings.

## Examples (DRAFT)
This section contains two almost minimal examples showing on a small variety of configuration options.  Check the `config` folder in SGCT for more examples.

Here is a minimal example of a single node, single window configuration.  This file creates a single node on `localhost` with a single window that has a size of 1280 by 720 pixels with a camera of 80 degrees horizontal field-of-view and approximately 50.5 degrees vertical field of view.
```json
{
  "version": 1,
  "masteraddress": "localhost",
  "externalcontrolport": 20500,
  "nodes": [
    {
      "address": "localhost",
      "port": 20401,
      "windows": [
        {
          "fullscreen": false,
          "name": "OpenSpace",
          "stereo": "none",
          "pos": { "x": 50, "y": 100 },
          "size": { "x": 1280, "y": 720 },
          "viewports": [
            {
              "pos": { "x": 0.0, "y": 0.0 },
              "size": { "x": 1.0, "y": 1.0 },
              "projection": {
                "type": "PlanarProjection",
                "fov": {
                  "hfov": 80.0,
                  "vfov": 50.534015846724
                },
                "orientation": { "yaw": 0.0, "pitch": 0.0, "roll": 0.0 }
              }
            }
          ]
        }
      ]
    }
  ],
  "users": [
    {
      "eyeseparation": 0.065,
      "pos": { "x": 0.0, "y": 0.0, "z": 0.0 }
    }
  ]
}

```
The following example is a configuration that creates two nodes, both running on the local machine, the difference being that their field-of-views are rotated by 40 degrees off the center.
```json
{
  "version": 1,
  "masteraddress": "127.0.0.1",
  "nodes": [
    {
      "address": "127.0.0.1",
      "port": 20401,
      "windows": [
        {
          "fullscreen": false,
          "pos": { "x": 0, "y": 300 },
          "size": { "x": 640, "y": 360 },
          "viewports": [
            {
              "pos": { "x": 0.0, "y": 0.0 },
              "size": { "x": 1.0, "y": 1.0 },
              "projection": {
                "type": "PlanarProjection",
                "fov": {
                  "hfov": 80.0,
                  "vfov": 50.534015846724
                },
                "orientation": { "yaw": -20.0, "pitch": 0.0, "roll": 0.0 }
              }
            }
          ]
        }
      ]
    },
    {
      "address": "127.0.0.2",
      "port": 20402,
      "windows": [
        {
          "fullscreen": false,
          "pos": { "x": 640, "y": 300 },
          "size": { "x": 640, "y": 360 },
          "viewports": [
            {
              "pos": { "x": 0.0, "y": 0.0 },
              "size": { "x": 1.0, "y": 1.0 },
              "projection": {
                "type": "PlanarProjection",
                "fov": {
                  "hfov": 80.0,
                  "vfov": 50.534015846724
                },
                "orientation": { "yaw": 20.0, "pitch": 0.0, "roll": 0.0 }
              }
            }
          ]
        }
      ]
    }
  ],
  "users": [
    {
      "eyeseparation": 0.065,
      "pos": { "x": 0.0, "y": 0.0, "z": 4.0 }
    }
  ]
}

```

The final example is a fisheye rendering which demonstrates a more sophisticated rendering setup, which internally consists of many projections that are automatically assembled by SGCT into a single circular fisheye output.
```json
{
  "version": 1,
  "masteraddress": "localhost",
  "nodes": [
    {
      "address": "localhost",
      "port": 20401,
      "windows": [
        {
          "name": "OpenSpace",
          "fullscreen": false,
          "stereo": "none",
          "size": { "x": 512, "y": 512 },
          "viewports": [
            {
              "pos": { "x": 0.0, "y": 0.0 },
              "size": { "x": 1.0, "y": 1.0 },
              "projection": {
                "type": "FisheyeProjection",
                "fov": 180.0,
                "quality": "1k",
                "tilt": 27.0,
                "background": { "r": 0.1, "g": 0.1, "b": 0.1, "a": 1.0 }
              }
            }
          ]
        }
      ]
    }
  ],
  "users": [
    {
      "eyeseparation": 0.06,
      "pos": { "x": 0.0, "y": 0.0, "z": 0.0 }
    }
  ]
}
```

# Element types
The rest of the documentation contains information about the different types of XML nodes that can be added to the configuration files.  For the nomenclature, *Attributes* are parameters of an XML node where as *Children* are child XML node of the node that is currently discussed.  Some *Attributes* are maked as *optional* which means that they do not have to be present and their default behavior depends on the particular option, which is mentioned in the description.  For *Children*, it is mentioned how many children are allowed or have to be preset for a specific node.

# Element types (DRAFT)
The rest of the documentation contains information about the different types of JSON properties that can be added to the configuration files. The JSON configuration file contains one object that encapsulates all the settings that we want to pass to OpenSpace - this is everything between the first open `{` and last closing `}`. In between these curly brackets we can a set of *Properties* that themselves contains other *Properties* or *items*. Some *Properties* are maked as *optional* which means that they do not have to be present and their default behavior depends on the particular option, which is mentioned in the description.  For *Items*, it is mentioned how many items are allowed or have to be preset for a specific node.

 - [Capture](config/capture)
 - [Cluster](config/cluster)
 - [Device](config/device)
 - [Node](config/node)
 - [Projections](config/projection/index)
   - [CylindricalProjection](config/projection/cylindricalprojection)
   - [EquirectangularProjection](config/projection/equirectangularprojection)
   - [FisheyeProjection](config/projection/fisheyeprojection)
   - [PlanarProjection](config/projection/planarprojection)
   - [ProjectionPlane](config/projection/projectionplane)
   - [SphericalMirrorProjection](config/projection/sphericalmirrorprojection)
   - [SpoutOutputProjection](config/projection/spoutoutputprojection)
 - [Scene](config/scene)
 - [Settings](config/settings)
 - [Tracker](config/tracker)
 - [User](config/user)
 - [Viewport](config/viewport)
 - [Window](config/window)
