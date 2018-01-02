# Quiz 5: Animations and Mechanim

## Animations in 2D
- built out of frames
- use a Sprite Atlas
- use an engine called Mechanim

## Mecanim
- Animator View 
- Animator Controller

## Scripting
- Triggers
- Transition conditions
- Coroutines
- Unity API

### Using Animations
- Loop Time:
	- option in Animation Inspector
	- whether the animation loops or not
- Animation View:
	- shows time and sprite displayed
	- can rearrange
	- expand the animation clip to preview each frame

#### Creating an Animation Clip
- Window > Animation > Create New Clip
- Save as asset
- name
- place under Assets/Content/Animations folder
- Animation Controller is created automatically, new clip is added as *default state*

#### Animator Controller
- Create > Animator Contrller in Project View
- gets created automatically when a new Animation Clip is created
- gets created when a collection of sprites are dragged to the scene
- Animation Controller + Clips
- has **states** that require animations to play
	- e.g. Idle, Run, Jump
- contains **state machines** that determine which animations are played
	- states
	- transitions
	- triggered conditions
- **current state** : only in one state at a time

#### Default State
- first state that executes
	- e.g. Idle
- right click on a state to set it to default

#### State Transitions
- click on a state> Add Transition
- point to state to transition to
- Transitions are one-directional
- Transition Duration
	- time in seconds transition takes to complete
	- increasing = transition is slower

#### Conditions
- checks logic
- default is Exit Time
	- duration to wait within a state before transitioning

#### Parameters
- control animation states
- get values from script code
- when parameter changes, state transition checks if it satisfies the **transition condition**
	- e.g. (speed > 1)
- created by clicking + icon
- Parameter Types:
	- Float
	- Int
	- Bool
	- Trigger
- Set parameter name and type

### Animation Scripting
- requires a reference to the Animation Component

```Csharp

//reference to Animator component
Animator anim =
	this.gameObject.GetComponent<Animator>();

//pass values to Animator parameters using Set methods
anim.SetInteger("DoorState", 1);
anim.SetFloat("Speed", 2.3f);
anim.SetBool("IsFiring", true);
anim.SetTrigger("Jump");

```

### Animation View
- Samples
	- sets how many frames make up a second of animation
	- reduce to make slower
- << and >>
	- navigate between keyframes of animation
- play button
	- preview animation
- changes made while RECORD button is on will be applied to the current sleected frame
- Add Curve:
	- select which properties to modify in frame
	- x, y, z axis
- can select which Function the event will call
	- function exists in script attached to the animated gameObject

### Animation Scripting
- an animation callback method can be private
	- executable code passed as an argument to another code
	- e.g. DestroyMe() as an Animation function


#### SetActive
- SetActive(false)
	- deactivate game object
	- make an object and its **children** invisible in the scene
	- halt exe of all components and scripts in hierarchy
```cSharp
someGameObject.SetActive(false);
```
- SetActive(true)
	- activate game object
	- make object and its children visible
	- re-enable components that were previously disabled
```csharp
someGameObject.SetActive(true);
```

#### activeSelf, activeInHierarchy
- boolean values
- activeSelf
	- whether it has been activated or deactivated using SetActive
- activeInHierarchy
	- whether obj has been activated or deactivated using SetActive on one of it's parents and not itself
- use these to check if gameObject is visible
- activeSelf more common use than activeInHierarchy


