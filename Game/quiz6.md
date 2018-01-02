# Quiz 6 : Animations 3D
- Mechanim animations
- Quaterions

## Mechanim
- Unity's animation state machine system
- create states that play animations and define transition logic to move between states
- use if you have imported .fbx characyer with a rig
	- of any time
- must be defined as **humanoid** or **generic**
	- Mechanim does not work with legacy imported characters and animations

## Mechanim Parts
### Animator
- component attached to animated characters
- Animated Controller:
	- node based system
	- defines state machines
	- handles transitions
- Avatar
	- definition for your rig
	- use to retarget animations with same rig
	- avatar will automatically be generated for an .fbx
- Apply Root Motion
	- tell Mechanim to use the root motion of character to move
	- can uncheck this to control motion through code
		- less realistic animation	
		- footslide
		- if animation and speed don't match

### Animator Controller
- required
- system of creating Mechanim animation states and trnasitions
- create states and transition logic

### States
- single node
- motion or blendtree used by state
- speed of state
- Mirrored or Not
	- e.g. mirroring movement (left turn, right turn, etc)
- list of all transitions from this state to any other state

### Transition
- moving from one state to another
- similar to 2D transitions
- based on conditions
- can have multiple conditions

### Parameters
- can configure in animator contorller
- click + button
- types
	- Int
	- Float
	- Bool
	- Trigger
- blendspace
	- param that determines how much blending between motions

### Layers
- overlay and overwrite animations across character
- control animation on specific parts of the body
- e.g. base = body, separate layer = face
- All animator controllers start with a base layer

### Animation Avatar
#### Humanoid rigs and avatars
- avatar = definition of your rig
- Unity has basic humanoid definition
- drawing a map between Unity's "idea" of a humanoid rig and your rig

#### Generic rigs and avatars
- could be anything non-humanoid
- avatar is making a new definition based off of bones in the rig

### Avatar
- by default, new avatar is defined for every .fbx import
- ideally: import bind-pose character .fbc with mesh and create a New Avatar
- import animations on the character as skeleton only
- copy avatar from the T-pose
- only keep one definition of the rig
- only one copy of the mesh
- one import of textures and materials

## Quaternion
- rotation
- complicated math
- x, y, z, w
- product of two vectors:
	- how much energy is going in original direction
	- boost speed
	- energy absorption
	- complicated formula in slide under "Dot Product of Two Vectors"

### Functions
- Quaternion.LookRotation
	- creates a rotation with specified forwards and upwards directions
- Quaternion.Angle
	- returns angle in degrees between two rotations a and b 
- Quaternion.Euler
	- returns a rotation that rotates z degrees around z axis, x degrees around x axis, y degrees around y axis
- Quaternion.Slerp
	- spherically interpolated between a and b by parameter t
	- t clamped to range [0,1]
- Quaternion.FromToRotation
	- creates roation which rotates from fromDirection to toDirection
	- rotate a transform so one of the axes follows a target direction toDirection in world space
- Quaternion.identity
	- corresponds to "no rotation"
	- object is perfectly aligned with world or parent axes

### Why Quaternions?
- 3D rotations can be represented by 3 number (e.g. Euler angles)
	- non-linear
	- difficult to work with
- e.g. we can't map the surface of the earth without distorting either angles or areas



