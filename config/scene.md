---
title: Scene

parent: Configuration Files
---

This node determines an overall orientation of the scene.  It consists of an `Offset`, an `Orientation`, and `Scale`;  all of which is included in the projection matrix that is passed to the rendering function callback of the specific application.  This node can be used to customize the rendering for a specific rendering window.  A common use-case in planetariums, for example, is to account for a tilt in the display system by providing an `Orientation` with the same pitch as the planetarium surface.  This makes it possible to reuse the same application between the planetarium dome and fixed setups without the need for special care.

# Children
`Offset` \[ 0 - 1 \]
 > A linear offset of the scene center.  Must define three float attributes `x`, `y`, and `z`.  The default values are `x=0`, `y=0`, `z=0`, which means that no offset is applied to the center of the scene.

`Orientation` \[ 0 - 1 \]
 > Describes a fixed orientation of the global scene.  This can be provided either as Euler angles or as a quaternion.  The two modes *cannot* be mixed.  The following descibes the different attributes that can be used for the orientation.  Please note that *all* attributes for the chosen method have to be specified.
 > 
 > Euler angles:
 >  - `pitch` or `elevation`: negative numbers tilt the camera downwards;  positive numbers tilt upwards.  The allowed range is \[-90, 90\].
 >  - `yaw`, `heading`, or `azimuth`: negative numbers pan the camera to the left;  positive numbers pan to the right.  The allowed range is \[-360, 360\].
 >  - `roll` or `bank`: negative numbers rotate the camera to the left;  positive numbers to the right.  The allowed range is \[-180, 180\].
 > 
 > Quaternion:
 >  - `x`
 >  - `y`
 >  - `z`
 >  - `w`
 > 
 >  Example:  `<Orientation pitch="20.0" elevation="-12.0" roll="0.0" />`

`Scale` \[ 0 - 1 \]
 > A scaling factor for the entire scene.  The default value is `1.0`.
