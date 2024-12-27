# BlogPost 9 - Individual reflections

This last blog post is intended to document my reflections on the development process of the project. Since I worked as a one-person-team, I have full knowledge about all the issues there were during the development process, so I will reference both technical aspects, as well as personal worries and thoughts.

### The AR project - Animal Crossing: New Horizons AR Museum extension

For a more in depth description of code and last minute changes, you can read the additional “BlogPost 8”, where I described my struggles and more technical issues. I believe that would give a better impression of what was going on during the last stages of the development process.

This AR project was presented as an extension to the existing game “Animal Crossing: New Horizons”, specifically, the museum related gameplay of the game. The main idea was about scanning physical cards with an Android device, with which a person would be able to collect critters and save them inside the Critterpedia. This Critterpedia would serve as an encyclopedia, where the user could access the collected critters and read fun information about them. 

The technologies used were the Unity 6 Game Engine, using the ARCore framework, since the app was developed for Android devices, and Adobe Photoshop and Blender for creating visuals and 3D models. 

The project was more or less successful, with the main idea implemented fully, and less successful about implementing small details I wanted to add in order to make the experience more immerseful and maximize the AR features that Unity can offer. As of right now, the project makes use of the image-tracking feature. I analyzed this more in depth in “BlogPost 3”. I created real-life cards with 3 different prints, which I added inside the Reference Image Library. 

![Screenshot_1](https://github.com/user-attachments/assets/0f53f72b-81e5-47f3-849f-954a6d0bc959)

Then, using the AR Tracked Image Manager script and a hand-made AR Image Tracking script  inside the AR Session Origin object, I managed to connect the images with the corresponding Scriptable objects, holding the critters information. 

![Screenshot_2](https://github.com/user-attachments/assets/cc49a842-fe09-4113-8d13-bc849e1853ca)

Initially, the image tracking feature was intended to be used differently, to be precise, the user was supposed to scan the card and see a 3D model appear on the screen of the Android device. During the early stages of development, this was indeed possible. Even though there were issues with the 3D model behavior, specifically its placement on the card (you can read more about it in “BlogPost 2” and “BlogPost 3”, as well as see a demo of the feature),this feature was later overlooked, as there were more critical issues going on, and also the chosen testing strategy made it difficult to keep track of it (more about testing in “BlogPost 3”). Right now you can encounter glimpses of code and fields in different game objects that are intended to accommodate this feature, but they are not functional.  

Originally, the project also intended to include motion tracking and plane finding (in the context of raycasting) (see more about it in “BlogPost 2”). These would’ve been used in order to create a real museum experience, where the user would apply different 3D models from the app library inside the scene, using the objects around him. Unfortunately, because of the lack of resources and unexpected difficulties, these plans were put to the side, and I decided to concentrate on perfecting the core functionality of the project. 

Other features besides the ARCore related ones include the dialogue and library systems. The dialogue feature was created as a guide that would help the user understand how the app works and what actions should be done. You can see the full dialogue in the demo presentation video.  

The dialogue system heavily relies on the actions taken by the user. For example, the user would have to click on the big center button once launching the app, to trigger Tom Nook’s dialogue lines. Then, the dialogue would stop and only continue once the system detects 3 distinct critters inside the library (Critterpedia). 

![Screenshot_3](https://github.com/user-attachments/assets/144d9b06-cf55-4617-a5e6-a0a47d91b921)

After that, the dialogue with Blathers would appear only after the user clicks on a menu button, but that menu button would only appear after 3 distinct critters were collected.  

![Screenshot_4](https://github.com/user-attachments/assets/1979ca07-350d-4a16-a5d7-e3fec52435c8)
![Screenshot_5](https://github.com/user-attachments/assets/9d25f55f-9ca3-4263-85a9-be7dd01ac506)

This was done as part of the immersive effect and connection to the original source. As the project was intended as a fun and educational experience for children, I felt that including the popular characters, as well as a detailed guide, would make the experience effortless. Also, coming from my work experience in the LEGO Branded Games department, a lot of test sessions for different games proved how crucial quality guides are - since the majority of people tend to play games based on intuition and ignore guides, for them then to struggle with identifying features and having an unpleasant experience because of that, it is very important to more or less impose fun and useful guides. And so, this is what I’ve done too - the guide will not let the user continue if the necessary actions were not done, and even though I think that I should’ve included more straightforward indications, the dialogues proved that their implementation was needed.

As for the library feature - I figured that it would be a good way of keeping the project afloat in the long run, since it gives a reason for the user to come back to the game. Of course, if I managed to implement the whole original plan, the Critterpedia would’ve been even more useful, but right now it still holds a key feature, that is reviewing the collected critters. As of the current version, it mostly resembles the original Critterpedia from the source game.  

The functionality is best showcased in the following 3 functions inside the CriterpediaManage script: InitializeSlots(), AddCritterToPedia() and ShowCritterDetailsImage(), and the OnSlotTapped() function inside the CritterpediaSlot script.

![Screenshot_6](https://github.com/user-attachments/assets/692a4f20-527d-44c2-b69c-fa51e9b1df14)
![Screenshot_7](https://github.com/user-attachments/assets/1b6d12b8-033e-4097-a8fa-c2911d391b61)
![Screenshot_8](https://github.com/user-attachments/assets/19a8e8f0-0588-43f6-972b-46e886876b17)
![Screenshot_9](https://github.com/user-attachments/assets/c609962b-900d-4534-b456-313401bdd95a)

Of course there is more to the implementation than this, but it’s generally about setting up the data and graphics, since the app is heavily populated with visuals, and not necessarily actual features development. As I also mentioned in “BlogPost 7” and ”BlogPost 8”, this library feature is very similar to an inventory system in a game - the entity data is packed as a Scriptable Object, that is collected by a collecting manager and sent to a slot inside the library or inventory. The slot would then be marked as occupied, so the next entity can be stored inside another slot. From there, the user would be able to navigate to the library and interact with an entity, that would result, in this case, in accessing an infocard about the critter. 

### The VR project - VR Medieval Tavern

Compared to the previous AR project, the VR project proved to be way less complex, due to its similarity in development to any other ordinary game, which I already had experience with developing, and the very good base that the XR Interaction Toolkit provided. 

The technologies I used are the above mentioned XR Toolkit, paired with the Unity Game Engine, the Oculus Meta Quest 2 headset and Blender. The features I used in the project are using the Interaction Components, the XR Rig, the Input System controllers and Locomotion system, including teleportation, and immersive sound, using the Audio Affordance Receiver script. Originally, I also planned to use the Hand Tracking feature, but due to the custom body I used for the user, that would’ve looked rather weird and more or less difficult to implement. 

Starting with the scene and character creation - for this project I used an already existing scene I created a while ago (see “BlogPost 5” for more details), that I had to strip of unnecessary topology, in order to make the objects less heavy memory-wise and import into a Unity scene. There, I transformed the majority of objects that the user would realistically be able to interact with into rigid bodies, and applied colliders to them, including the floor and walls. I also attached the XR Grab Interactable and the XR General Grab Transformer to the objects the user would interact with, for a realistic feeling of playing around with objects (see more details about it in “BlogPost 7”). I also extended the scene a bit and added planes with images of a road and taverns, to better blend in the imported 3D tavern and enhance the immersiveness. 

For the player’s body, I sculpted and rigged a humanoid cat (see more details in “BlogPost 6”), and imported it into the Unity scene, where I used the skeleton built in Blender and rigged it using Inverse Kinematics, to assign movement constraints and directions for the limbs to look organic while moving. I ended up only assigning this to the arms, as they were the easiest, thanks to the headset controllers. The reason why I decided to create a character is rather simple - a lot of the VR tutorials and games I saw didn;t have a body, so the objects the user was interacting with seemed to float in the air, which looked unnatural, so I decided to go full on and create a whole character. 

Also, I just wanted to try something new, as it was my first time sculpting something specific and that would be used, and same goes for rigging. 

In terms of locomotion, I used the basic locomotion provided by the XR Toolkit - through the XR Body Transform component, and the “turn” and “move” provider components, that would allow the user to turn their head left and right, and dynamically move 2-dimensionally inside the scene (along the X and Z axis of the scene), and the teleportation anchors (more about locomotion see in “BlogPost 5”). This was rather simple, as I just set up the Teleportation Area to cover the full scene, and a couple of anchors to which the player could stick to. 

During the rigging process, I did encounter minor issues with locomotion. Even though I didn’t mendel with any of the locomotion functionalities, it seems like some type of overwriting did happen along the way (I truly have no idea when and where), so I wrote a script that would limit the movement and only allow it along the X and Z axis. 

![Screenshot_10](https://github.com/user-attachments/assets/f1b8b06b-9653-42e3-a8ff-7381469b134e)
![Screenshot_11](https://github.com/user-attachments/assets/0c793cf9-3172-4cf0-9405-dfd41ec3d683)

Another VR related feature I implemented is the immersive sound. To give more life to the tavern and make it more or less believable, I added 3 audio sources, with the necessary components attached - XR Intractable Affordance State Provider and Audio Affordance Receiver. Inside the fields of the second, I assigned the Affordance State Provider component within the same object, the Audio Source component and the Affordance Theme Datum. For the Audio Theme, I set the audio clip as idle, so that it would play continuously. 

![Screenshot_12](https://github.com/user-attachments/assets/34351e0d-74fa-4a79-91c1-af798522864d)

So now, in game, once the player gets further away from one audio source they can hear it less, and the other way around. 

Other unrelated VR features include a mirror, which I implemented using a Rendered Texture (see details in “BlogPost 6”), and generally another big part of work was the scene setup, using volumetric fog and lights. For this, I used URP, which is not ideal, solely because HDRP doesn’t work on VR headsets, or at least on the one I developed for. This is why some of the lights act strangely and generally I could not mimic the ambience I created once for this scene in Blender.

### Summing up

Generally, these projects served as good practice. Building for other devices besides the PC was a new experience for me, and I haven’t expected the amount of difficulties I would stumble upon, and can’t even imagine how the development process would’ve been without today’s advanced SDKs, which, especially in the case with VR, do the majority of work and were very easy for me to use. Quite frankly, I believe that if I stuck only to what the framework could provide me with, the process would’ve been way smoother, but I do not feel remorse - the opposite, I am glad that I managed to make it work - combine the special framework features with my own. 

The learning path was kind of chaotic, mostly because there is no fixed structure of how things should be done, and the vast possibilities one has for implementation. It surely took me out of my comfort zone, but I’d say it also elevated my skills and deepened my knowledge of Unity and its features. I was also finally able to implement assets from my external experience and make use of them. I totally do not regret being in a one-person-team, because this gave me whole autonomy of the projects, and I could learn from every second of the development process, and not only contribute to a project that I would be oblivious about some of its aspects. 
