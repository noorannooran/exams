# Building a platformer game

## Part 1
- make platforms into 1 piece
- add a collider to the collider (box or edge)
- add player person
	- add rigidbody
	- add collider (capsule maybe)
- in player controller script
- Serialize Field:
- forceMultiplier
- var for rigidbody and animator
- Start function: get them in script from the gameObject
- FixedUpdate function (synchronized with the clock)
	- get the axis
	- add force
- this moves the dude left and right

## Making Hero Move Left and Right

```csharp
//char move left and right
void FixedUpdate(){
	Vector2 forceVect = new Vector2(
			Input.GetAxis("Horizontal"),
	);

	_rigidBody.AddForce(forceVect + forceMultiplier);

	if(_rigidBody.velocity.x >0){
		gameObject.transform.localScale = new Vector3(-1, 1, 1);
	}
	else if (_rigidBody.velocity.x > 0){
		gameObject.transform.localScale = new Vector3(1, 1, 1);
	}

```

## Making Hero Jump
- Serialize Field
- private float jumpMultiplier

### In FixedUpdate()
- float jump = Input.getAxis("Jump");

```csharp
if(jump >0){
	_rigidBody.AddForce(Vector2.up * jumpMultiplier);
}

```

## Is Grounded Method Using RayCast

```csharp
private bool IsGrounded(){
	SpriteRenderer sr = gameObject.GetComponent<SpriteRenderer>();
Vector2 pos = gameObject.transform.position;
RaycastHit2D res = Physics2D.Linecast{
	new Vector2(pos.x, pos.y = (sr.bounds.size.y/2)),
	new Vector2(pos.x, pos.y = (sr.bounds.sizey/2+0.2f))
	);

	Debug.DrawLine = Physics2D.Linecast{
	new Vector2(pos.x, pos.y = (sr.bounds.size.y/2)),
	new Vector2(pos.x, pos.y = (sr.bounds.sizey/2+0.2f))
	);

	return res != null && res.collider!= null;
}

```
- call in jump function if(jump > 0 && IsGrounded())


## Killzone
- On bottom of level so that you die/ respawn at the start of the level
- Empty Object called Killzone, take to the bottom
- Add an edge collider to it
- Add script to it

```csharp
[SerializeField]
Transfortm spawnPoint = null; //enter this later

public void OnCollisionEnter2D(Collision2D other){
	other.transform.position = spawnPoint.position;
	Rigidbody2D rb = other.gameObject.GetComponent<RigidBody2D>()'
	if(rb){
		//cancel velocty
		rb.velocity = Vector2.zero;
	}
}


```
- make sure the player doesn't have the velocity that they had when falling
- create spawn point (empty gameObject - move to above the platform) - assign to KillZone script

## Create script that allows camera to follow the player
```csharp
//script CameraFollow

[SerializeField]
Transform target = null;


void Update(){
	gameObject.transform.position =
		new Vector3(target.position.x,
				target.position.y,
				gameObject.transform.position.z);

}

```
- why use gameObject transform position?
	- we don't want the camera to be rotating

## Add Animation to Scene to show player running
	- delete from scene
	- delete controller (need only the animation)
- you know how to do this part!!
- add parameters so that not constantly running
- velocity (0)
	- take out wait time for transitions
	- we are going to test in PlayerController

- when player moves
- _animatior.SetInteger("velocity",(int)(Mathf.Abs(_rigidBody.velocity.x));


## Adding Jump animation
- add animation
- add new variable (Bool)
	- jump
- transition to jump from idle, and run
- condition: when jump is true
- transition back to run if jump is false and velocy greater than 0
- tansition back to idle if velocity is equal to zero and jump is false

- _animator.SetBool("jump", !IsGrounded());
	- if not grounded, you are jumping

## Part 2
- Adding enemy
- Add the sprite
	- add rigidbody2d
	- add collider
- Add EnemyController
	- will need speed
	- will need the rigidbody2D
	- the transform
	- the width and height

```
void Start(){
	_rigidBody = gameObject.GetComponent<RigidBody2D>();
	_transform = gameObject.transform;

	SpriteRenderer sprite = gameObject.GetComponent<SpriteRenderer>();
	_ width = sprite.bounds.extents.x;
	_height = sprite.bounds.extents.y;

}

void FixedUpdate(){
	//USE RAYCASTER TO CHECK IF THERE IS GROUND TO MOVE
	//move down and to the left
	Vector2 lineCastPos = 
		(Vector2)_transform.position + 
		(Vector2)_transform.right * _width - 
		(Vector2)_transform.up * _height;	

	Debug.DrawLine(lineCastPos, lineCastPoos+Vector2.down);
	bool isGrounded =
		Physics2D.LineCast(lineCastPos, lineCastPos + Vector2.doqn);
	
	if(isGrounded)
	{
		Vector3 curRot = _transform.eulerAngles;
		curRot.y += 180;
		_transform.eulerAngles = curRot;

	}
	
	Vector2 vel = _rigidBody.velocity;
		vel.x = _transform.right * speed;
		_rigidBody.velocity = vel;
}

```

### Create a door
- take platform, rotate it
- when player jumps there, it will slide down,
- when snowman comes out door will close again
- add collider
- add another collider to be the trigger
	- stick out toward the player so only player can open it
- add script to the door gameobject

```csharp
	[SerializeField]
	private float closeDelay = 2f;
	[SerializeField]
	private float speed = 0.1f;
	[SerializeFiled]
	private float openPosition;
	[SerializeField]
	private float closePosituon;

	private bool isOpen = false;

	void Start(){
	//make sure in closed position
		gameObject.transform.position =
					new Vector2(gameObject.transform.position.x, closedPosition);
	}

	void OnTriggerEnter2D(Collider 2D other){
		StartCoroutine("Open");	
	}	
	
	private IENumerator Open(){
		if(!isOpen){
			isOpen = true;
			//open door
			for(float p = closdPosition; p >= openPosition; p= p-speed){
				gameObject.transform.position =
					new Vector2(gameObject.transform.position.x, p);
			}
			yield return new WaitForSeconds(0.1f);
		}
	}
	
	//do opposite of open
	private IENumberator Close(){
		if(isOpen){
			isOpen = false;
			//close door
			for(float p = openPosition; p <= closedPosition; p = p + speed){
				gameObject.transform.position =
					new Vector2(gameObject.transform.position.x, p);
			}
			yield return new WaitForSeconds(0.1f);
		}
			}	
		}
	}	

```

# Part 3 
## Projectiles
- add sprite (cloud)
- add rigid body
- add collider
- add script to the Player to shoot projectiles
	- ProjectileShoot
- add script attached to the gameObject Projectile
	- Projectile
- save projectile as prefab
- edit prefab scripts

## ProjectileShoot Script
- trigger animation
- create projectile

```csharp
[SerializeField]
private GameObject projectile;
[SerializeField]
private float projectileForce = 500f; //play with this number

private Animator _animator = null;

private Transform _transform = null; //players transform

Start(){
	_animator = gameObject.getcomponent<Animator>();
	_transform = gameObject.ransform;

}

Update(){
	if(Input.GetKeyDown(KeyCode.F)){	
	_animator.SetTrigger("fire");
	//create object and make fly
	//FireProjectile();
	}
}

void FireProjectivle(){
	//instantiate projectile
	GameObject p = Instantiate(projectile,	//projectile game object
				_transform.position, //position of player
				Quaternion.identity); //not rotation

	RigidBody2D rb = p.GetComponent<RigidBody2D>();
	
	//ignore the collision between player and projectile
	Physics2D.IgnoreCollision(
			gameObect.GetComponent<collider2D>(); //collider from player
			p.GetComponent<Collider2D>(); //collider from projectile

	//add force to the projectile
	rb.AddForce(-(_transform.right) //player by default is facing left
			* projectileForce 
			* _transform.localScale.x); //if the player is flipped
	p.transform.localScale = _transform.localScale;
}


```
- assign prefab of projectile to script
- have to make sure the projectile doesnt interact with player
	- move the spawn of projectile to infront of the player
	- ignore the collsion

### Add animation to the player
- drag attack animation to the scene, delete the object in scene, delete the controller
- go to Animator : add the animation to the animator
	- add transition from Any State to Fire animation
	- no exit time
	- condition: fire (trigger)
- make transition from Fire Animation back to Idle
	- exit time set : when fire is finished
- animation looks weird: change FireProjectile to the animation
- select player -> Window-> Animation -> Select Fire
	- add event somewhere in the middle
	- select FireProjectile()

### Projectile Script
- don't want to have projectiles firing forever
- should disappear automatically
- with a coroutine

```
[SerializeField]
int damage = 10; //set from Unity

void Start(){
	StartCoroutine("Finish");
}

//handle collision
void OnCollisionEnter2D(Collision2D other){
	//instead of checking what the object is
	IDamageable d = other.gameObject.GetComponeent<IDamageable>();
	if(d!=null) //if object is damageable
	{
		Damage(damage);
	}
	Destroy(gameObject);
}

private IENumerator Finish(){
	yield return new WaiForSeconds(1);
	Destroy(gameObject);
}

//object that will implement this interface will have health, health will be affected by this
//eg. if the projectile hits the enemy
public interface IDamageable{
	void Damage(int damage);
}
```
- modify enemy make damageable

### EnemyController
```

[SerializeFiled]
int _health = 10;

public void Damage(int d)
{
	_health -= d;
	if(_health <=0){
		Destroy(gameObject);
	}
}
```
- can have exactly same approach with player

### Player Controller
- add health Serialize Field
- add Damage function

```csharp
int _health = 100;
bool dead = false;

	void Damage(int d){
	_health -=d;
	if(_health<=0){
	dead = true; //set 
	_animator.SetBool("dead", dead); //start death animation
	gameObject.SetActive(false); //player does not interact with anything anymore
	}
	}
```

- if not dead when fall into kill zone - respawn
- go back to enemy and make sure when ti collides with player, player takes damage


EnemyController

```csharp
void OnCollisionEnter2D(Collision2D other){
	IDamageable d = other.gameObject.GetComponenet<IDamageable>();
	if(d!= null && other.gameObject.GetComponent.tag.Equals("Player"))
	{
		d.Damage(30);
	}
}

```
- if we leave this : eenmey can kill other enemy
- add condition that other object must be player
- make sure player has tag player
- add die Animation to the Hero GameObject
	- from any state
	- with bool "dead"

## To change scene
- have class SceneManager
- using Unity.SceneManager

```csharp
 SceneManager.LoadScene(1); //index
```
- build settings: make sure all scenes are listed there (drag and drop)
- use name or index in Inspector