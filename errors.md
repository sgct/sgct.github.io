---
nav_order: 6
---

# Errors
SGCT uses unique error codes in the case when an unrecoverable error occurs that cannot be dealt with internally.  This page contains additional information about each error code and how to mitigate such an error if they occur.  The basic structure of the codes are that each block of 1000 numbers belongs to a different component of SGCT.  Additionally, individual components can use additional grouping as they see fit, but in general the first number in the error code identifies which component the error code came from (the component will also be named in the log message that is output).  You can also find a listing of all error codes in the `error.h`.

1. [1000s](#1000s-configuration)
1. [2000s](#2000s-correction-meshes)
1. [3000s](#3000s-engine)
1. [4000s](#4000s-mpcdi)
1. [5000s](#5000s-network)
1. [6000s](#6000s-xml-configuration-parsing)
1. [7000s](#7000s-shader-handling)
1. [8000s](#8000s-window)
1. [9000s](#9000s-image)


## 1000s: Configuration
### 1000
> \[User\] Eye separation must be zero or a positive number`

### 1001
> \[User\] Tracking device name must not be empty

### 1002
> \[User\] Tracking tracker name must not be empty

### 1003
> \[User\] Name 'default' is not permitted for a user

### 1010
> \[Capture\] Capture path must not be empty

### 1011
> \[Capture\] Screenshot ranges beginning has to be before the end

### 1020
> \[Settings\] Swap interval must not be negative

### 1021
> \[Settings\] Refresh rate must not be negative

### 1030
> \[Device\] Device name must not be empty

### 1031
> \[Device\] VRPN address for sensors must not be empty

### 1032
> \[Device\] VRPN address for buttons must not be empty

### 1033
> \[Device\] VRPN address for axes must not be empty

### 1040
> \[Tracker\] Tracker name must not be empty

### 1050
> \[Planar Projection\] Up and down field of views can not be the same

### 1051
> \[Planar Projection\] Left and right field of views can not be the same

### 1060
> \[Fisheye Projection\] Field of view setting must be positive

### 1061
> \[Fisheye Projection\] Left and right crop must not overlap

### 1062
> \[Fisheye Projection\] Bottom and top crop must not overlap

### 1063
> \[Fisheye Projection\] Quality value must be positive

### 1064
> \[Fisheye Projection\] Quality setting only allows powers of two

### 1065
> \[Fisheye Projection\] Diameter must be positive

### 1066
> \[Fisheye Projection\] All background color components have to be positive

### 1070
> \[Spherical Mirror Projection\] Quality value must be positive

### 1071
> \[Spherical Mirror Projection\] Quality setting only allows powers of two

### 1072
> \[Spherical Mirror Projection\] All background color components have to be positive

### 1080
> \[Spout Output Projection\] Mapping name must not be empty

### 1081
> \[Spout Output Projection\] Quality value must be positive

### 1082
> \[Spout Output Projection\] Quality setting only allows powers of two

### 1083
> \[Spout Output Projection\] All background color components have to be positive

### 1090
> \[Viewport\] User must not be empty

### 1091
> \[Viewport\] Overlay texture path must not be empty

### 1092
> \[Viewport\] Blendmask texture path must not be empty

### 1093
> \[Viewport\] Blendmask level texture path must not be empty

### 1094
> \[Viewport\] Correction mesh texture path must not be empty

### 1095
> \[Viewport\] No valid projection provided

### 1100
> \[Window\] Window name must not be empty

### 1101
> \[Window\] Empty tags are not allowed for windows

### 1102
> \[Window\] Number of MSAA samples must be non-negative

### 1103
> \[Window\] Monitor index must be non-negative or -1

### 1104
> \[Window\] MPCDI file must not be empty

### 1105
> \[Window\] Window must contain at least one viewport

### 1106
> \[Window\] Cannot use an MPCDI file and explicitly add viewports simultaneously

### 1107
> \[Window\] First window cannot be blitted into as there is no source

### 1110
> \[Node\] Node address must not be empty

### 1111
> \[Node\] Node port must be non-negative

### 1112
> \[Node\] Node data transfer port must be non-negative

### 1113
> \[Node\] Every node must contain at least one window

### 1120
> \[Cluster\] Cluster master address must not be empty

### 1121
> \[Cluster\] Cluster external control port must be non-negative

### 1122
> \[Cluster\] There must be at least one user in the cluster

### 1123
> \[Cluster\] More than one unnamed users specified in the cluster

### 1124
> \[Cluster\] No two users can have the same name

### 1125
> \[Cluster\] All trackers specified in the 'User's have to be valid tracker names

### 1127
> \[Cluster\] Configuration must contain at least one node

### 1128
> \[Cluster\] Two or more nodes are using the same port


## 2000s: Correction Meshes
### 2000
> \[Correction Mesh\] Failed to export. Geometry type is not supported"

### 2001
> \[Correction Mesh\] Failed to export " + exportPath + ". Failed to open"

### 2010
> \[Dome Projection\] Could not determine format for warping mesh

### 2020
> \[MPCDI Mesh\] Configuration error. Trying load MPCDI to wrong viewport

### 2021
> \[MPCDI Mesh\] Error reading from file. Could not find lines

### 2022
> \[MPCDI Mesh\] Invalid header information in MPCDI mesh

### 2023
> \[MPCDI Mesh\] Incorrect file type. Unknown header type

### 2030
> \[OBJ\] Failed to open warping mesh file

### 2031
> \[OBJ\] Vertex count doesn't match number of texture coordinates

### 2040
> \[Paul Bourke\] Failed to open warping mesh file

### 2041
> \[Paul Bourke\] Error reading mapping type

### 2042
> \[Paul Bourke\] Invalid data

### 2050
> \[Pfm\] Failed to open %s

### 2051
> \[Pfm\] Error reading from file

### 2052
> \[Pfm\] Invalid header syntax

### 2053
> \[Pfm\] Incorrect file type

### 2054
> \[Pfm\] Error reading correction values

### 2060
> \[Scalable\] Failed to open warping mesh file

### 2061
> \[Scalable\] Incorrect mesh data geometry

### 2070
> \[SCISS\] Failed to open warping mesh file

### 2071
> \[SCISS\] Incorrect file id

### 2072
> \[SCISS\] Error parsing file version from file

### 2073
> \[SCISS\] Error parsing type from file

### 2074
> \[SCISS\] Error parsing view data from file

### 2075
> \[SCISS\] Error parsing file

### 2076
> \[SCISS\] Error parsing vertices from file

### 2077
> \[SCISS\] Error parsing indices from file

### 2078
> \[SCISS\] Error parsing faces from file

### 2080
> \[SimCAD\] Error parsing XML file

### 2081
> \[SimCAD\] Error reading XML file. Missing 'GeometryFile'

### 2082
> \[SimCAD\] Error reading XML file. Missing 'GeometryDefinition'

### 2083
> \[SimCAD\] Not the same x coords as y coords

### 2084
> \[SimCAD\] Not a valid squared matrix read from SimCAD file

### 2090
> \[SkySkan\] Not a valid squared matrix read from SimCAD file

### 2091
> \[SkySkan\] Data reading error


## 3000s: Engine
### 3000
> \[Engine\] Failed to initialize GLFW

### 3001
> \[Engine\] Requested node id was not found in the cluster configuration

### 3002
> \[Engine\] When running locally, a node ID needs to be specified

### 3003
> \[Engine\] Computer is not a part of the cluster configuration

### 3004
> \[Engine\] No sync signal from master after X seconds

### 3005
> \[Engine\] No sync signal from clients after X seconds

### 3006
> \[Engine\] Error requesting maximum number of swap groups

### 3010
> \[Engine\] GLFW error


## 4000s: MPCDI
### 4000
> \[MPCDI\] Failed to parse position from XML

### 4001
> \[MPCDI\] Failed to parse size from XML

### 4002
> \[MPCDI\] Missing child element 'frustum'

### 4003
> \[MPCDI\] Failed to parse frustum element. Missing element

### 4004
> \[MPCDI\] Failed to parse frustum element. Conversion error

### 4005
> \[MPCDI\] Require both xResolution and yResolution values

### 4006
> \[MPCDI\] No 'id' attribute provided for region

### 4007
> \[MPCDI\] Multiple 'buffer' elements not supported

### 4008
> \[MPCDI\] GeometryWarpFile requires interpolation

### 4009
> \[MPCDI\] Only linear interpolation is supported

### 4010
> \[MPCDI\] GeometryWarpFile requires path

### 4011
> \[MPCDI\] No matching geometryWarpFile found

### 4012
> \[MPCDI\] Cannot find XML root

### 4013
> \[MPCDI\] Error parsing MPCDI, missing or wrong 'profile'

### 4014
> \[MPCDI\] Error parsing MPCDI, missing or wrong 'geometry'

### 4015
> \[MPCDI\] Error parsing MPCDI, missing or wrong 'version'

### 4016
> \[MPCDI\] Missing 'display' element

### 4017
> \[MPCDI\] Multiple 'display' elements not supported

### 4018
> \[MPCDI\] Missing 'files' element

### 4019
>\[ MPCDI\] Unable to open zip archive file

### 4020
> \[MPCDI\] Unable to get zip archive info

### 4021
> \[MPCDI\] Unable to get info on file

### 4022
> \[MPCDI\] Unable to open XML file

### 4023
> \[MPCDI\] Read from XML file failed

### 4024
> \[MPCDI\] Unable to open PFM file

### 4025
> \[MPCDI\] Read from PFM file failed

### 4026
> \[MPCDI\] MPCDI does not contain the XML and/or PFM file

### 4027
> \[MPCDI\] Error parsing main XML file


## 5000s: Network
### 5000
> \[Network\] Failed to parse hints for connection

### 5001
> \[Network\] Failed to listen init socket

### 5002
> \[Network\] Bind socket failed

### 5003
> \[Network\] Listen failed

### 5004
> \[Network\] Failed to init client socket

### 5005
> \[Network\] Failed to set network no-delay option: %s

### 5006
> \[Network\] Failed to set reuse address: %s

### 5007
> \[Network\] Failed to set send buffer size to %d. %s

### 5008
> \[Network\] Failed to set receive buffer size to %d. %s

### 5009
> \[Network\] Failed to set keep alive: %s

### 5010
> \[Network\] Error in sync frame %i for connection %i

### 5011
> \[Network\] Failed to uncompress data for connection %i: %s // Sync Connection

### 5012
> \[Network\] Failed to uncompress data for connection %i: %s // Data Transfer

### 5013
> \[Network\] TCP connection %i closed: %s

### 5014
> \[Network\] TCP connection %i receive failed: %s

### 5015
> \[Network\] Send data failed: %s

### 5020
> \[Network Manager\] Winsock 2.2 startup failed

### 5021
> \[Network Manager\] No address information for this node available

### 5022
> \[Network Manager\] No address information for master available

### 5023
> \[Network Manager\] Port %i is already used by connection %i

### 5024
> \[Network Manager\] Failed to compress data: %s

### 5025
> \[Network Manager\] No port provided for connection to %s

### 5026
> \[Network Manager\] Empty address for connection to %i

### 5027
> \[Network Manager\] Failed to get host name

### 5028
> \[Network Manager\] Failed to get address info: %s


## 6000s: XML configuration parsing
### 6000
> \[Planar Projection\] Missing specification of field-of-view values

### 6001
> \[Planar Projection\] Failed to parse planar projection FOV

### 6010
> \[Projection Plane\] Failed parsing coordinates. Missing XML children

### 6011
> \[Projection Plane\] Failed parsing ProjectionPlane coordinates. Type error

### 6020
> \[Viewport\] Unrecognized eye position

### 6021
> \[Viewport\] Failed to parse position. Type error

### 6022
> \[Viewport\] Failed to parse size. Type error

### 6030
> \[Window\] Could not parse window position. Type error

### 6031
> \[Window\] Could not parse window size. Type error

### 6032
> \[Window\] Could not parse window resolution. Type error

### 6040
> \[Node\] Missing field address in node

### 6041
> \[Node\] Missing field port in node

### 6050
> \[Settings\] Wrong buffer precision value. Must be 16 or 32

### 6051
> \[Settings\] Wrong buffer precision value type

### 6060
> \[Capture\] Unknown capturing format. Needs to be png, tga, jpg

### 6070
> \[Tracker\] Tracker is missing 'name'

### 6080
> \[XML Parsing\] No XML file provided

### 6081
> \[XML Parsing\] / Could not find configureation file: %s

### 6082
> \[XML Parsing\] / Error parsing XML file

### 6083
> \[XML Parsing\] / Cannot find 'Cluster' node

### 6084
> \[XML Parsing\] / Cannot find master address

### 6085
> \[XML Parsing\] / Unknown color bit depth %s

### 6086
> \[XML Parsing\] / Unknown resolution %s for cube map

### 6090
> \[Spout Output\] Unknown spout output mapping: %s

### 6100
> \[Spherical Mirror\] Missing geometry paths


## 7000s: Shader Handling
### 7000
> \[Shader Manager\] Cannot add shader program %s: Already exists

### 7001
> \[Shader Manager\] Could not find shader with name %s

### 7010
> \[Shader Program\] No shaders have been added to the program %s

### 7011
> \[Shader Program\] Error linking the program %s

### 7012
> \[Shader Program\] Failed to create shader program %s: Already created

### 7013
> \[Shader Program\] Failed to create shader program %s: Unknown error


## 8000s: Window
### 8000
> \[Window\] Error opening GLFW window


## 9000s: Image
### 9000
> \[Image\] Cannot load empty filepath

### 9001
> \[Image\] Could not open file '%s' for loading image

### 9002
> \[Image\] Filename not set for saving image

### 9003
> \[Image\] Cannot save file %s

### 9004
> \[Image\] Could not save file %s as JPG

### 9005
> \[Image\] Could not save file %s as TGA

### 9006
> \[Image\] Missing image data to save PNG

### 9007
> \[Image\] Can't save %d bit

### 9008
> \[Image\] Can't create PNG file '%s'

### 9009
> \[Image\] Failed to create PNG struct

### 9010
> \[Image\] Failed to create PNG info struct

### 9011
> \[Image\] One of the called PNG functions failed

### 9012
> \[Image\] Invalid image size %i x %i %i channels
