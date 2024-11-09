# BlogPost 5 - Lab 4 - VR Project presentation

The fifth Blogpost is done to document the confirmed idea, as well as the beginning of the development process. 

### What is the project about?

The purpose of this project is to create a VR interactive experience of a cat bartender in a medieval setting. It would represent some of the VR features that I’ve learned in class, work between platforms and connection/build to the Oculus VR headset, as well as showcase some of my external skills, such as modeling and rigging a 3D character, as well as Unity functionalities knowledge.

### What will the project look like?

I will be using a scene I previously made in Blender, of a medieval style tavern. I would need to modify it a bit to cater to this project. The player would be acting as a cat bartender, mixing and pouring drinks, counting coins, and other bartender activities. Additionally, I would like to add a mirror to the scene, which the player will be able to use and see themselves (ideally). Also there will be a possibility to teleport to different tables in the tavern, to see what’s happening there as well and/or look at them in detail. 

![orth](https://github.com/user-attachments/assets/259bb54c-f84c-436d-b4f3-eedbf444dac8)
![cam1](https://github.com/user-attachments/assets/5b6ee4ec-b829-4105-a50a-115c3fba089d)
![cam3](https://github.com/user-attachments/assets/04aee1e4-f2cf-44cc-9b99-12de5fdce9d4)

### Delimitations

- I’ve never rigged a 3D character before;
- I’m kinda bad at 3D animations. 

### Technologies

The technologies used in this project include the Oculus Meta Quest 2 from the hardware perspective, and from the software perspective, the Unity Game Engine with the Unity XR SDKs, along with Photoshop (UI elements) and Blender (the player character, environment and interactive elements). 

### How is the process going? 

The process is going fine until now. I started by optimizing my environment assets as much as possible. Since I chose to work with a scene I have previously created, I did not bother too much with optimisation, since Blender can render big amounts of data without too much trouble. For a comfortable experience in VR though, the max amount is 300k tris. This way, I reduced the amount from 417.5k to around 158k. 

![tavern original](https://github.com/user-attachments/assets/af9f4fd6-9c5d-4db2-8452-73b38ea22340)
![tavern after clean up](https://github.com/user-attachments/assets/5c4443ea-fdfa-491c-bd25-4253de097f1b)

I also deleted the faces outside of the tavern, this is why it looks so weird on the outside, both in Blender and Unity. Even more in Unity, since it just doesn’t render the inverted faces. 

![tavern in unity](https://github.com/user-attachments/assets/d7f6c693-75e2-4a11-9132-751c86663b4c)

After this, the first step of the environment set up was more or less done. I only had to fix some materials, attach colliders and fix some gaps that would make the player fall through the floor. To make the experience more immersive, I added some planes on the outside of the tavern, such as the road and other buildings. 

To improve the experience even more, I decided to add some volumetric fog and lights. Right now it all looks pretty bad - the skybox and fog play their roles nicely, but I still have some work left on the lights. In my opinion, it is all too bright, as the main lighting should come from the candles and the moonlight. In Blender it is very easy to set it up, but in Blender it is easy to work with rendering pipelines and everything is straight forward. In Unity, I first tried to do some research regarding rendering pipelines, and came to the conclusion that I would need HDRP, which in the end, apparently doesn’t work on Android platform. I remained on URP and worked with what I could, so let’s see what can I do with the ambience. 

![environment inspector](https://github.com/user-attachments/assets/ee55aafb-99b9-4adc-af21-6c6e626d084b)

Since I own a headset, I had the majority of the set up in place, so connecting it all wasn’t an issue. I also used the “Basic Scene” that comes with the VR template project, and transferred some objects from the “Starting Scene” to the one I worked on.

One of the VR native functionalities I already included is teleportation. I set up a couple of anchors, one behind the bar and another in the scene among the tables. Locomotion is in place and correctly set up, so the player can now also move freely in the scene. 

![bar teleport](https://github.com/user-attachments/assets/7ba34d47-5383-4867-88d3-6048ec23e043)

Please visit this link to see the first version of the project: https://youtu.be/WBAygWJRE9s

### What are the next steps?

First, I would like to fix the ambience and make it look at least more realistic. Then, I would like to model the player - the cat bartender. Here is a concept of what it would look like, but in my mind it would be a bit more chubby, so the final version might differ. I would also rig it accordingly and set the skeleton to work right in VR. 

![GG](https://github.com/user-attachments/assets/4b6ddf42-949a-4f5a-94d3-190cecf1f273)

The reason I want to create the character first, is because next I want to implement a mirror, where the player can look at themselves. It promises to be a quick and easy implementation. And finally, I would like to be able to introduce interactables - grab and toss around objects as minimum, and actually pour drinks in glasses and mugs, with animations and sound as maximum. Besides the sound effects of animations, I would also like to add a background sound of a busy tavern. 
