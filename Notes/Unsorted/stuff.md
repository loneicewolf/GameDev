# unsorted stuff
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5b1eb5ec-88f7-481e-9b81-204a5f8ae1d8" />



# music to listen to while gamedev'ing:
- https://youtu.be/AehGUvB2jJ4?t=253 guitar danganronpa 
- [Climax Reasoning」Danganronpa: Trigger Happy Havoc / Extended ](https://www.youtube.com/watch?v=FVVJ7Zjmtpw&list=RDFVVJ7Zjmtpw&start_radio=1)
- [Danganronpa: All Investigation Themes 2017](https://www.youtube.com/watch?v=AehGUvB2jJ4)
- note, maybe try to play danganronpa some time? i haven't


# RESOURCES
- **Resources** https://docs.godotengine.org/en/stable/about/list_of_features.html

- https://claude.ai/new
- https://gemini.google.com/app
- https://chatgpt.com




# PROBLEMS AND SOLUTIONS
- docs help me to get a overview
- GPT Helps me a bit to begin
- right now i think i enjoy it[godot] actually cuz, it's so simple, button,menu,etc. < really nice!
- now i got into a button and i have no audio file, so I copied /usr/share/sounds OR /usr/share/audio FILES, and then, it only needed mp3 so..
  - https://askubuntu.com/questions/442997/how-can-i-convert-audio-from-ogg-to-mp3
  - `ffmpeg -i usr_share_freedesktop_stereo_bell.oga usr_share_freedesktop_stereo_bell.mp3` this should work ig
  - did it work in godot? [Y/N]: Yes
  - some simple problems like, "cant attach node cuz no script or whatever > make new script etc and try again, yep works!" and "no scene selected, select this one? yep." 
  

  <img width="1168" height="721" alt="image" src="https://github.com/user-attachments/assets/929a8af2-34cd-4010-be9f-488fa5f8da1e" />

  - plays the `ffmpeg -i usr_share_freedesktop_stereo_bell.oga usr_share_freedesktop_stereo_bell.mp3`  if button pressed

  # so far so good! 


# It didn't take me long to make this! woah!
- <img width="663" height="317" alt="image" src="https://github.com/user-attachments/assets/0efca165-ab07-475c-a22d-ed3d537c86b1" />
- https://bsky.app/profile/did:plc:37lcyqfy4d5r25jvgtabe5kn/post/3m57h6bg3kc24
- with this kind of music (danganronpa) anything seems to be possible! *vibin* xD https://youtu.be/FVVJ7Zjmtpw?list=RDFVVJ7Zjmtpw&t=70



# ======================================================= PROGRESS =======================================================
## playing around with it a bit
<img width="1376" height="773" alt="image" src="https://github.com/user-attachments/assets/a314b487-6229-45a5-aca3-66485d06fb73" />
<img width="1376" height="774" alt="image" src="https://github.com/user-attachments/assets/6b6174d2-102c-4cb6-89d8-89447ff73893" />
<img width="1349" height="705" alt="image" src="https://github.com/user-attachments/assets/aa358601-814a-4b11-aba5-b4f9253c699c" />



# errors on the way
```
###############
#GPT ON THE parse error on calling from caesar_puzzle.gd TO THIS file CIPHER_csr .gd
# FROM func caesar_cipher(text: String, shift: int) -> String:
# TO   static func caesar_cipher(text: String, shift: int) -> String:
### COPY OF THE caesar_puzzle.gd Err code:
##########
### SOLVED 1
	## var encrypted = Cipher.caesar_cipher(input_text, 3)
	## ERROR: Parse Error: Cannot call non-static function "caesar_cipher()" on the class "res://CIPHER_csr.gd" directly. Make an instance instead.
	## GPT: just make the func static
	### SOLVED 1
##########
###############
```



# progress update 2

<img width="850" height="363" alt="image" src="https://github.com/user-attachments/assets/7db60350-91d6-4236-a3ff-7436c388c3f5" />

- play
-
<img width="751" height="275" alt="image" src="https://github.com/user-attachments/assets/2b1aca77-8f48-477d-b2c1-da11fde46606" />
<img width="328" height="205" alt="image" src="https://github.com/user-attachments/assets/6563e409-d5f5-4d98-b052-58571b65ebb1" />
<img width="703" height="301" alt="image" src="https://github.com/user-attachments/assets/f6bbe227-9e71-4b01-a872-de67f4286af6" />
<img width="633" height="205" alt="image" src="https://github.com/user-attachments/assets/ffc62c13-80f9-43a9-9df4-6d17927140ce" />

play works
	back works
	encrypt works
	check works
	input text works
quit works







# Problems


Q: I needed a sound effect for a button
A: 
	1. open in terminal in the THIS FOLDER
	2. mkdir -p ./assets/{audio,pics}
	3. # cp /usr/share/sounds/freedesktop/stereo/bell.oga ./assets/audio
	4. # ffmpeg -i assets/audio/bell.oga assets/audio/bell.mp3


# Q: Why not use OGA?
# A: I tried, didn't load/play properly. (I think)


# Q: if no sound but "all is right"
# A: -> unmute.


if no sound but "all is right" -> unmute. In settings, 
