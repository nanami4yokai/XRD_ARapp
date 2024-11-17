# BlogPost 6 - Lab 5 - VR Project update

This blogpost serves to showcase my progress with the project, what I managed to implement and what poses issues, as well as my plans for the future week. 

### What progress has been made?

Generally, I've been managing to implement my desired features smoothly. No delays are expected so far.  

I've managed to create the body of the player (the Cat character) in Blender, give it some materials and a skeleton. 

![cat bare no rig](https://github.com/user-attachments/assets/88b20b60-4b4a-47bd-b341-6241bac04141)
![cat bare](https://github.com/user-attachments/assets/524dd6ac-8e30-4e96-81dd-c08b30c2b9e9)
![cat texture and rig](https://github.com/user-attachments/assets/9ad8be7b-498a-4935-975c-c511727837f7)

[leg rig goes brr](https://youtube.com/shorts/UX3VBgJDdqM?feature=share)

I imported it into Unity just fine and rigged it using Inverse Kinematics, in accordance with the controllers. Basically I created a VR Constraint game object with a Rig component, under the Cat (rigged character) game object, and added objects with the Two Bone IK Constraint component for the arms, legs and head. Those components keep track of the structure of the skeleton, assigning targets (usually the ends of the chains of bones, aka palms and feet and the head itself), and hints (the bones that bend the limb, thus dragging the rest of the chain after them, aka joints). I kept the controllers' interaction functionality, as the model of the controllers would just be covered by the paws, even though not perfectly. 

![Screenshot_3](https://github.com/user-attachments/assets/cbe82c80-2ab1-4e74-a0f8-ffa19b041c01)
![Screenshot_2](https://github.com/user-attachments/assets/b862d414-f9fd-4a34-a3ea-cac8b8f87204)
#
![Screenshot_1](https://github.com/user-attachments/assets/df08bef4-197a-4926-b767-ad36739b802b)

The locomotion features were kept intact as well, even though some scripts I used for rigging interfered with them. 

[Vr locomotion gone wrong](https://youtu.be/PFCjzcagLsY)

*please excuse the bg music, it was late in the night when I was developing and became desperate when suddenly the locomotion didn’t work when I haven’t even touched it, so I put some 2010’s mix to gain back my enthusiasm for the process* 🫠

I also managed to create the mirror just fine. I used a Rendered Texture for it, rendering a camera output placed right before the mirror game object. I also used some script that would make the window work realistically, by tracking the player’s position in the scene and showcasing a phenomenon known as the mirror-mediated perception, when the angle at which a person looks in the mirror, determines what part of the environment is visible in the reflected image. Unfortunately, it ended up messing with the cameras, so I had to delete it. 

![Screenshot_5](https://github.com/user-attachments/assets/6090c02b-d321-4197-b915-a701efb0a6b1)
![Screenshot_6](https://github.com/user-attachments/assets/460076b6-e153-4000-a347-773fb4f75ee5)

I also added some medieval tavern background sounds and music, by placing some game objects with the XR Intractable Affordance State Provider, Audio Source components and the Audio Affordance Receiver script, that would allow me to assign an Affordance Theme Datum. I set them to play the audio clip in a loop, in an idle state, so the music would always play. 

![Screenshot_7](https://github.com/user-attachments/assets/75c72943-d285-467a-a302-abae43b89ac7)
![Screenshot_8](https://github.com/user-attachments/assets/b01309cb-1fde-4e7c-9f27-c2c7ba7e36ac)

The multiple objects around the scene make the experience immersive, so depending on where you stand in the scene, you can hear the sound worse or better. 

![Screenshot_4](https://github.com/user-attachments/assets/6588a156-d62c-4a53-b889-063f4ad25901)

### What are the next steps?

Next, I would like to work with interactables. I would like to set almost everything in the scene as an intractable (that would not require major physics implementations) as a fun way to play in the scene. During the development of my GMD project I only concentrated on implementing interactivity to objects that were necessary for the progress of the game, but some funsies here and there would’ve made the experience much more fun.  

Besides this, I would also like to implement the original plan of actually acting as a barman, and pour drinks in different cups and mugs. That would include animations and physics, so let’s see how that goes. 

In the end I would like to also make some refinements of the environment and the Cat model, since right now the paws are looking pretty broken. 
