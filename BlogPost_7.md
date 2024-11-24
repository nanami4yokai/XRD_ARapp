# BlogPost 7 - Lab 6 - VR Project final update

This blog post is the last in the chain, and it is intended to present the final updates of the development process of my VR project. I will also describe the whole process for a bit and sum it up, emphasizing the most VR related features in the project. 

### What progress has been made since last time?

Since the last thing I wanted to implement were interactables, I modified the majority of the objects on the tables. To achieve this, I attached a couple of components to the game objects:

![rigidbody inter](https://github.com/user-attachments/assets/5273a676-1c65-47b0-8cc8-ce42d8d2811f)

I assigned a mass of 10 to the items, to give them a bit of gravity force. Also, set the collision detection to continuous, so they collide with things on runtime. 

![xr grab interact](https://github.com/user-attachments/assets/48244ed7-8ee6-4438-b116-74b67d6ba3b3)

Some of the fields I modified are the movement type, set to Velocity Tracking for a smooth grabbing and throwing interactions. Also, I enabled the Throw on Detach field, so when the objects are released, they gain velocity and therefore realism. Next, I enabled the Use Dynamic Attach field, so that depending on where the object is grabbed from, it determines the relative offset to the controller, again, allowing for more realism.

![xr general grab interact](https://github.com/user-attachments/assets/02850120-0de2-481f-89b7-ed3b1554ec7e)

I also attached mesh colliders to the objects that would interact with the mugs, coins and so on,  and the character. 

[VR Tavern interactables](https://youtu.be/ybBaQD_eXbs)

I chose to derive from the original plan of implementing the liquid pouring functionality, due to multiple reasons. First, due to change in height (if the player is sitting/standing/just has different heights), if you look down, the body (head) of the character is interfering and the player can’t see anything behind it, so that would be annoying, since one would need to look down to see the animation. 

Second, that would need more time for development, since I couldn’t really find any guides besides simulating the pouring effect using the particle system, and independent liquid-in-a-bottle simulations. So coming up with some physics and making the animation could bring unexpected difficulties, which I do not have the time for.  

So this is the last update I will be doing to the project. Let’s sum up a bit and rewind the VR features I used to create the project.

Starting with the cat bartender character, which I created and rigged outside of Unity. Once imported into Unity, I used Inverse Kinematics to attach the bones to the VR controllers and head gear, creating targets and hints that would allow for the limbs to bend in the right direction (see BP 6 to see details). 

The method did work, but unfortunately it still needs a bit of polishing, and I also didn’t necessarily consider height constraints, so now if I stretch my hands out of bounds and/or move them quickly, the limbs will bend awkwardly. I also rigged the legs, but of course there are no controllers for leg movement monitoring, so it would need some additional functionality, that would basically calculate the XR camera position in the scene and move the bones in such a way that the legs would follow the body. I did not implement this feature though, because of multiple reasons, including lack of resources, like to-date guides on how to do it, and time.

Another XR inherited feature is player's locomotion, which I simply copied from the original scene that the project template is coming with. And same with controllers’ interaction. 

Following with the scene and the objects inside it (see BP 5 for more details) - I used a scene I already created in Blender and reduced the tris to be able to import it into Unity and render it using the headset, as well as use a bit of post processing. I did all the usual things needed in a 3D game, but besides that I also set some of the objects in the scene as XR interactables, meaning that the player can interact with them using the controllers (see above for more details). 

I also added some immersive sounds so it feels like a real tavern. For that I used special XR components so the sounds would feel real, depending on where the player is in the scene relating to the sound source (see BP 6 for details). 

