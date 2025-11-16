- TEMPLATE: BASIC 3D MOVEMENT
- References used: Docs, Manual, YT, Stack*Sites, own experience(even if new)
- A note on GPT: Do NOT rely only on it, always verify, because it's often actually wrong, at least the new 5.1 in my experience(s) even when THINKING HARD. Hallucinates often. *Might try PRO again and see if that makes a diff.*
- See FURTHER READINGS Below

## GUIDE
New 3D project, New 3DNode Scene
Add the following nodes as the following:
- **World**
- Floor (**`Static`Body3D**) -> adjust a bit
  - CollisionShape3D -> Box
  - MeshInstance3D -> Box
- Player (**`Character`Body3D**)
  - Camera3D -> Move a bit above CollisionLines(CTRL for snap)
  - CollisionShape3D -> Capsule

```bash
for i in move_{forward,back,left,right}; do echo "$i"; done
```

## SCRIPTS

- ATTACH TO: Player (`CharacterBody3D`)
- SCRIPTNAME: `player.gd`
```
extends CharacterBody3D

# === MOVEMENT SETTINGS ===
@export var speed: float = 5.0
@export var jump_velocity: float = 4.5
@export var mouse_sensitivity: float = 0.002

# === INTERNAL STATE ===
var yaw: float = 0.0
var pitch: float = 0.0
var gravity: float = ProjectSettings.get_setting("physics/3d/default_gravity")

func _ready() -> void:
	Input.set_mouse_mode(Input.MOUSE_MODE_CAPTURED)

func _unhandled_input(event: InputEvent) -> void:
	if event is InputEventMouseMotion:
		yaw -= event.relative.x * mouse_sensitivity
		pitch -= event.relative.y * mouse_sensitivity
		pitch = clamp(pitch, -1.5, 1.5)
		rotation.y = yaw
		$Camera3D.rotation.x = pitch

func _physics_process(delta: float) -> void:
	var direction: Vector3 = Vector3.ZERO

	# Movement (WASD)
	if Input.is_action_pressed("move_forward"):
		direction -= transform.basis.z
	if Input.is_action_pressed("move_back"):
		direction += transform.basis.z
	if Input.is_action_pressed("move_left"):
		direction -= transform.basis.x
	if Input.is_action_pressed("move_right"):
		direction += transform.basis.x

	direction = direction.normalized()

	# Gravity
	if not is_on_floor():
		velocity.y -= gravity * delta

	# Jump
	if Input.is_action_just_pressed("jump") and is_on_floor():
		velocity.y = jump_velocity

	# Movement apply
	velocity.x = direction.x * speed
	velocity.z = direction.z * speed

	move_and_slide()

```


# FURTHER READINGS/SCREENSHOTS/VISUAL DOCS
<img width="1120" height="214" alt="image" src="https://github.com/user-attachments/assets/02a5c736-5d10-4523-b698-636673fbfc69" />


```bash
for i in move_{forward,back,left,right}; do echo "$i"; done
move_forward
move_back
move_left
move_right
```
