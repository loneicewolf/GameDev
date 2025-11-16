- [ ] TODO: make a text version of this

New Control/Usr Scene, 

<img width="383" height="193" alt="image" src="https://github.com/user-attachments/assets/30e2976d-b81a-4834-a4f5-d8d00a7a40eb" />
<img width="1270" height="608" alt="image" src="https://github.com/user-attachments/assets/101cdf2e-6723-4215-9473-83f3961908e4" />

<img width="380" height="373" alt="image" src="https://github.com/user-attachments/assets/9cee5441-6f90-4735-b2d3-33d3f12ca296" />
<img width="339" height="196" alt="image" src="https://github.com/user-attachments/assets/46d624c5-af93-4ed6-bb4f-ff9077772911" />

<img width="241" height="98" alt="image" src="https://github.com/user-attachments/assets/0eddd0d3-88eb-44b6-8f33-9432ba9c4f1d" />


- References: DOCS, GPT, WorldDesignStackSite
- As usual double check GPT 

- main_menu.gd
```
extends Control

func _ready() -> void:
	Input.set_mouse_mode(Input.MOUSE_MODE_VISIBLE)
	$VBoxContainer/Button_Play.pressed.connect(_on_play_pressed)
	$VBoxContainer/Button_Quit.pressed.connect(_on_quit_pressed)

func _on_play_pressed() -> void:
	get_tree().change_scene_to_file("res://SCENES/World.tscn") # Loads Our MAIN World 


func _on_quit_pressed() -> void:
	get_tree().quit()
```


pause_menu.gd
```
extends CanvasLayer

var is_paused := false

func _ready() -> void:
	$VBoxContainer/Button_Resume.pressed.connect(_on_resume_pressed)
	$VBoxContainer/Button_Quit.pressed.connect(_on_quit_pressed)

func _input(event: InputEvent) -> void:
	if event.is_action_pressed("ui_cancel"): # usually ESC
		toggle_pause()

func toggle_pause() -> void:
	is_paused = not is_paused
	get_tree().paused = is_paused
	visible = is_paused
	if is_paused:
		Input.set_mouse_mode(Input.MOUSE_MODE_VISIBLE)
	else:
		Input.set_mouse_mode(Input.MOUSE_MODE_CAPTURED)

func _on_resume_pressed() -> void:
	toggle_pause()

func _on_quit_pressed() -> void:
	get_tree().paused = false
	get_tree().change_scene_to_file("res://SCENES/MainMenu.tscn")

```
