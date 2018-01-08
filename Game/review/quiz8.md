# Quiz 8 : Lights, Terrain, Scene
- Particle System Component (Shuriken)
- MinMax Curves
- Animated Particles VS Texture Sheets
- Scripting Particle Emissions

## Particle System Intro
- gameObject with particle System Component attached
- GameObject>Create Other> Particle System
- *translate*, *rotate*, *scale*
- particle-driven special effects:
	- rain
	- smoke
	- fire
	- sparks
	- magic
- involves **many small elements** that come together as a larger system
- **swarm of individual effects** that add up to a particle effect

## Particle System
### Parts:
1. Emitter
	- emits particles
	- controls **lifespan**
	- **emission rate**
	- **change through time**
2. Particle
	- basic element of system
	- controlled by emitter
	- a **billboard** facing the camera
		- 2D texture/ quad mesh
	- can also be a 3D object
Particle Lifespan:
	when it enters the particle system to when it leaves it

### More
- intended to be used in 3D space
- can be used in 2D but have no concept of sprites
- Sorting Layers can be set in scripts
	- **not** on a Particle system in Inspector


## Particle Effect ViewPort
- shown in **Scene View**
- controls *preview* of particle effect's playback
- changes made to preview controls **don't** affect
particle effect during runtime


## Particle System Inspector (Shuriken)
- shows up for currently selected particle system
- **Shuriken Editor**
	- uses Unity's Shuriken particle system to drive behaviour
- contains multiple **modules** shown as tabs in component view
- first module: **Particle System**

### Other Modules
- Emission
- Shape
- Velocity over Lifetime
- Limit Velocity over Lifetime
- Force over lifetime
- Color over lifetime
- Color by speed
- Size over lifetime
- size by speed
- Rotation over lifetime
- Rotation by speed
- External forces
- Collision
- Sub Emitters
- Texture Sheet Animation
- Renderer

### Modules
- Adds specialized behaviour to the particle system
- default: see all modules available
- shows modules that are not used
- **hide** and **show** disbaled modules using the (+) button
	- select which modules to show
- Deselecting **show all Modules**
	- condenses list to show only **currently enabled**

### Particle System
- Viewed by pressing Open Editor
- **Particle Effect Editor Window**
- contains all features of Shuriken

### Particle System VS Particle Effect
#### Particle Effects
- contain one or more Particle System components
	- parented to the same root
- edited in the **Particle Efffect wditor Window**

#### Particle System
- particle system components are edited in both
	- **Inspector View**
	- **Particle Effect Window**

## Min Max Crves
- change of values through time
- interpolate a curve/ line between two points

### Interpolation
- filling in values between two points
	- add additional points to define more complex changes through time
	- double click to add

### Colors and Gradients
- module properties deal with Color and Gradient editor
	- e.g. color over lifetime
	- color over speed

## Particle System module
- defines overall behaviour of particle system
- always present
- **cannot be removed or disabled**

### Properties
- Duration
	- duration of particle system
- Looping
	- whether loop once or forever
- Prewarm
	- looping systems start as if they've emitted particles for one cycle
- Gravity Modifier
	- gravity effects on particles
		- 1 = normal
		- 2 = double
		- 0.5 = half
- Inherit velocy
	- used for moving particles
	- spec. the amount of velocity to inherit from Parent Transform
- Simulation Space
	- Local or World space simulation
- Play on Awake
	- auto play Particle system when created
- Max Particles
	- max number that can be present in the scene at any one time

### Emission Module
- contols particle **emission rate**
- **bursts** of particles at certain moments within the duration
	- when a bunch of particles need to be created at once
	- e.g. explosions

### Shape Module
- shape of particle emitter
	- sphere
	- hemisphere
	- cone
	- box
	- mesh
- each shape has own properties
- emit from **shell** (edge) of shape
- emit from **volume** of shape

### Velocity Modules
- Velocity over Lifetime
	- animation control over particle
	- alter speed and direction over time
- Limit Velocity over Liftetime
	- limit velocity to set **maximum velocity threshold**
	- can be a **velocity vector** or **individiual axis**
		- (x, y, z)
- Force Over Lifetime
	- same as Velocity over lifetime
	- applies a force tot he particle

### Color Modules
- Color Over Lifetime
	- controls **color change** of each particle during its lifetime
	- shorter lifetime = **faster color change**
	- color acts a *tint*
	- **white color** == **no change**
- Color By Speed
	- same as color over lifetime
	- EXCEPT changes the color based on **speed**

### Size Modules
- Size Over Lifetime
	- controls change in particle size over lifetime
	- shorter lifespan = **faster size change**
- Size By Speed
	- same as size over lifetime
	- EXCEPT changes based on particle speed

### Rotation Modules
- Rotation Over Lifetime
	- controls particle rotation speed
	- in degrees/ second over lifetime
	- lifespan does not affect rotation speed
- Rotation By Speed
	- same as Rotation Over Lifetime
	- EXCEPT rotation speed is **based on particle movement speed**

### Collision Module
- enables collisions with a **flat plane** or **scene colliders**

#### Flat Plane Collision (Planar Collision)
- efficient
- planes defined by game object Transform

#### Scene Collider Collision (World Collision)
- uses ray casts to determine collisions with a collider shape
- can be performance-intensive
	- depends on collision quality

### Texture Sheet Animation Module
- enables particle to have an **animated texture**
- similar to how animated sprite sheets work
- texture sheet divided into a **grid of tiles**
- Cycles = number of cycles through the texture sheet during a particles lifespan
	- animation speed
	- more cycles = faster animation
- Frame Over Time
	- alters animation speed through particle's lifespan

### Renderer Module
- controls how particle is drawn on the screen
- **Render Mode**
	- spec. shape of the particle
- **Billboard**
	- particle into a flat plane (quad)
	- always faces the camera
- **Mesh**
	- uses custom 3D object instead of quad
- Specify the particle's Material in the renderer module

### Particle Material
- requires a material to be able to display a texture
- **Material** has a **shader** which takes at least one **texture** as input
- must have a defined **Material** asset in the project
- **cannot** use a sprite asset to define a particle
- **cannot** use a sprite sheet to play an animated texture on the particle

#### Steps
1. Define material asset
- Specify which shader it uses
- Provide a texture as input to the shader
- Assign material to the particle system

#### Steps: Animated Sprite Sheet on particle
1. create material asset whose texture is the sprite sheet
- apply that material to the particle system

### Scripting particle systems
- must have a reference to **ParticleSystem** componenet
- if ParticleEffect uses multiple particle systems, the ref will be to the **root* particle system
- make calls on the component:
	- Play(), Stop()
		- plays and stops particle system and all child particles

#### Variables
- duration
	- readonly duration of particle system in seconds
- emissionRate
	- rate of emission
- enableEmission	
	- set to false: not emit particles
- gravityModifier
- isPaused
	- is particle system paused?
- isPlaying
- isStopped
- loop
	- is particle system looping?
- maxParticles
	- max particles to emit
- particleCount
	- **readonly** current num of particles 
- playbackSpeed
	- 1 = normal
- playOnAwake
	- true = auto play on startup
- randomSeed
	- used for particle system emission	
	- set to 0: random value on awake
- safeCollisionEventSize
	- safe arraysize touse with ParticleSystem.GetCollisionEvents
- simulationSpace
	- space which to simulate particles
	- world / local
- startColor
- startDelay
- startLifetime
	- total lifetime in seconds particles have when emitted
	- using curves: scale on the curve
- startRotation
- startSize
- startSpeed
- time = playback position in seconds

#### Functions
- Clear
	- remove all particles in particle system
- Emit
	- emit count particles immediately
- GetCollisionEvents
	- get particle collision events of GameObject
	- return number of events written to array
- GetParticles
	- get particles of the system
	- returns num of particles written to input particle array
- IsAlive
	- does system have live particles
	- will system produce more?
- Pause
	- pauses particle system
- Play
	- plays particle system
- SetParticles
	- set particles, size is num of particled set
- Simulate	
	- ffwd the particle system
	- simulate particles over given period of time
	- pauses
- Stop
	- stop playing particle system




