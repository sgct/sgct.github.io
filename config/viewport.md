---
title: Viewport

parent: Configuration Files
---

This node describes a single viewport inside a [Window](window).  Every window can contain an arbitrary number of viewports that are all rendered independently.  The viewports are positioned inside the window using a normalized coordinate system.

# Attributes
`user` *optional* \[ string \]
 > The name of the [User](user) that this viewport should be linked to.  If a viewport is linked to a user that has a sensor, the positions of the sensor will be automatically reflected in the user position that is used to render this viewport.  The default is that no user is linked with this viewport.

`overlay` *optional* \[ string \]
 > This attribute is a path to an overlay texture that is rendered on top of the viewport after the applications rendering is finished.  This can be used to add logos or other static assets on top of an application.  The default is that no overlay is rendered.

`mask` *optional* \[ string \]
 > This value is a path to a texture that is used as a mask to remove parts of the rendered image.  The image that is provided in this should be a binary black-white image which is applied by SGCT after the application loading is finished.  All parts where the `mask` image is black will be removed.  The default is that no mask is applied.

`BlackLevelMask` *optional* \[ string \]
 > The file referenced in this attribute is used as a postprocessing step for this viewport.  The image should be a grayscale image, where each pixel will be multiplied with the resulting image from the application in order to perform a black level adaptation.  If a pixel is completely white, the resulting pixel is the same as the applications output, if a pixel is black, the resulting pixel will be back, if it is 50% grey, the resolution pixel will be half brightness.  The default is that no black level mask is applied.

`mesh` *optional* \[ string \]
 > Determines a warping mesh file that is used to warp the resulting image.  The application's rendering will always be rendered into a rectangular framebuffer, which is then mapped as a texture to the geometry provided by this file.  This makes it possible to create non-linear or curved output geometries from a regular projection by providing the proper geometry of the surface that you want to project on.  The reader for the warping mesh is determined by the file extension of the file that is provided in this attribute.  The default is that no warping mesh is applied.
 > Supported geometry mesh formats:
 > SCISS Mesh (`sgc` extension)
 > > A mesh format that was introduced by SCISS for the Uniview software.  SCISS created two versions for this file format, one for 2D warping meshes and a second for 3D cubemap lookups.  SGCT only supports the first version of the file format, however.
 > 
 > Scalable Mesh (`ol` extension)
 > > A mesh format created by [scalable](http://www.scalabledisplay.com/products/scalable-sdk/).
 > 
 > Dome Projection (`csv` extension)
 > 
 > Paul Bourke Mesh (`data` extension)
 > > A file format created by [Paul Bourke](http://paulbourke.net/dataformats/meshwarp/),  his webpage also contains more information abuot the individual steps of the warping.
 > 
 > Waveform OBJ (`obj` extension)
 > > The well known textual mesh format.
 > 
 > MPCDI (`mpcdi` extension)
 > > A subset of the VESA standard.
 > 
 > SimCAD (`simcad` extension)

`tracked` *optional* \[ boolean \]
 > Determines whether the field-of-view frustum used for this viewport should be tracking changes to the window configuration.  If this value is set to `false`, the field of view set in the beginning will stay unchanged.

`eye` *optional* \[ center, left, or right \]
 > Forces this viewport to be rendered with a specific eye, using the corresponding [User](user)s eye separation to compute the correct frustum.  If this value is not set, the viewport will be rendered according to the parent [Window](window)'s `stereo` attribute.

# Children
`Pos` \[ 0 - 1 \]
 > Specifies the position of the viewport inside its parent [Window](window).  The coordinates for `x` and `y`, which must both be specified in this node, are usually between 0 and 1, but are not restricted.  Parts of the viewport that are outside this range would lie outside the bounds of the window and are clipped.  Viewports are free to overlap and the viewports are rendered top to bottom into the window and can overwrite previous results.

`Size` \[ 0 - 1 \]
 > Specifies the size of this viewport inside its parent [Window](window).  The coordinate for `x` and `y`, which must both be specified in this node, are between 0 and 1, but are not restricted.  Parts of the viewport that are outside this range would lie outside the bounds of the window and are clipped.  Viewports are free to overlap and the viewports are rendered top to bottom into the window and can overwrite previous results.

Following are the different kinds of projections that are currently supported.  Exactly one of the following projections has to be present in the viewport.

 - [PlanarProjection](projection/planarprojection) \[ special \]
 - [FisheyeProjection](projection/fisheyeprojection) \[ special \]
 - [SphericalMirrorProjection](projection/sphericalmirrorprojection) \[ special \]
 - [SpoutOutputProjection](projection/spoutoutputprojection) \[ special \]
 - [Projectionplane](projection/projectionplane) \[ special \]
 - [Equirectangular](projection/equirectangular) \[ special \]
 - [Cylindrical](projection/cylindrical) \[ special \]
