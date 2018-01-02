# Quiz 7: Coroutines
> There is no powerpoint slide for this, so notes are from the Unity manual on Coroutines

## Coroutines
- a function that has the ability to pause execution and return control to Unity
- continue where left of in frame

```csharp
// Courotine declaration
IEnumerator Fade(){
	for (float f = 1f; f>=0; f-=0.1f){
		Color c = renderer.material.color;
		c.a = f;
		renderer.material.color = c;
		yield return null;
	} 
}
```

- return type of function is IEnumerator
- yield return statement in the body
	- execution will be paused

### Starting a Coroutine
- use StartCoroutine function

```csharp
//start coroutine
void Update()
{
	if (Input.GetKeyDown("f")){
		StartCoroutine("Fade");
	}
}
```

- loop counter maintains correct value over it's lifetime
- any variable or param is preserved between yields
- resumed on the frame after it yields

### WaitForSeconds
- introduce a time delay to the coroutine

```csharp
IEnumerator Fade(){
	for (float f = 1f; f>=0; f-=0.1f){
	Color c = renderer.material.color;
	c.a = f;
	renderer.material.color = c;
	yield return new WaitForSeconds(.1f);
	}
}
```

- spread an effect over time
- carry out tasks periodically **without** updating every single frame
	- e.g. an alarm that warns the player an enemy is nearby
	- if there are a lot of enemies, calling this == significant overhead
	- instead: use a coroutine to call every tenth of a second
- Coroutines are stopped only when a MonoBehaviour is destroyed
- not stopped when MonoBehaviour is disabled
- can stop a coroutine using:
	- MonoBehaviour.StopCoroutine
	- MonoBehaviour.StopAllCoroutines