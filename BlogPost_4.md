# BlogPost 4 - Lab 3 - Updates

The 4th Blogpost is the last one during the lab period designated for the AR project. In this document, I will describe how the development process has been, and try to sum up a part of the project implementation.

### Short sum up of features and implementation 

I will not go over the base AR configurations that must be present in the project, and instead go straight to what needs clarification. 

![Screenshot_7](https://github.com/user-attachments/assets/55394c9a-23b0-4a05-b344-b0277e36cc91)

Starting with the elements in the red group - these are just 2 buttons intended for dialogue trigger (see details further).They also hold the NPC script, that let me write in all the phrases I want the characters to say, as well as the specific images that would assign in the placeholders I will talk about in a bit.

![Screenshot_10](https://github.com/user-attachments/assets/1b637768-af88-4f67-b45b-54bf5b1e7dc6)

The orange group represents all the elements you will be able to see in the first video. Starting with the CritterCollecting_screen, that holds the CritterCollectingManager script, which manages what critter should be shown, depending on the IRL image that has been scanned.

![Screenshot_8](https://github.com/user-attachments/assets/7c695627-6992-4767-9b0d-b509a3c8ff46)

It also holds a reference to a button, the explanation to which you will see a bit later.
Next elements are simple - a group that would parent all the elements that need to fade in and out at the correct time, as well as message-images, that let the user know what exactly is happening after clicking one button or the other. And of course the said buttons - one that would add the critter to the critterpedia if possible, and the other that would just return to home screen without interacting with the critter. 

The yellow group is work in progress, which is pretty messy as of now, but you can read more about it later in the report.

The green group is managing the showcase of dialogs. None of the elements in this group actually manage the dialogues and delays (that is done by the DialogueManager game object), so it basically acts like a placeholder for the right images and text to appear depending on the progress in the game.

Then there is the blue group with the test UI that I talked about in the last blogpost. It really helps not having to go back and forth between PC and Android to test every minor feature that is added and exponentially increased my development speed, but it is fair to mention that occasional big tests on Android have to be taken, as with time it tends to give different results on the 2 platforms, that I then have to address. 

### How is the process going? 

Even though I’ve reached the end of the last lab week, I am still full into the development process. Last week I set a goal of finishing the implementation of the first half of the project, leaving object raycasting for a further period of refinement and experiment (autumn break), but as of right now I am struggling with the implementation of the Critterpedia. I adapted the last semester approach in the GMD course, when I also had to implement an inventory system. Thinking about it now, I might have made a mistake, since that time it took me a lot of effort and time to get it to work, so in the context of this project, I might have to revisit my plan.  

### What progress has been made? 

I managed to fix the animation issues, by moving from the “Animator with states” approach, to the “Fading in and out” approach using coroutines:

![Screenshot_4](https://github.com/user-attachments/assets/55aa75b0-02c1-4d29-b870-82bf5a54a26f)

A lot of debugging has been done due to issues, so there will be a lot of debug logs throughout the scripts. With this approach, the app became way less dynamic, in the sense that the user has to wait a pretty long time to let the animations play fully, but considering the circumstances, this would be the best option to go with. 

![bandicam2024-10-1301-08-47-032-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/c0c9120d-3977-4441-8156-4da2690ebdd1)

I also managed to implement the functionality of memorizing and adding data about critters to the critterpedia. Based on that, the correct message-image is displayed after interacting with a critter. I also modified the dialogue management a bit, though it’s only visible in the background, as I had to accommodate the new NPC interactions I wanted.  

![bandicam2024-10-1318-23-53-668-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/91edad22-4b4e-42cc-ae3b-be1044b909d7)

What I’ve done was to make Tom Nooks dialogue pause after the 3rd phrase, so it would allow the users to collect and deposit 3 critters in the Critterpedia. Once the 3 critters are caught, it resumes Tom Nook’s dialogue. 

![Screenshot_6](https://github.com/user-attachments/assets/74914f6b-be96-4171-8433-d5360128ef5b)

The dialogue pauses in DisplayNextSentence() when waitingForCritters is set to true after the 3 phrases have been shown. The dialogue will not proceed until ResumeDialogue() is called, which sets waitingForCritters back to false and allows the dialogue to continue. 

The end phrase of Tom Nook would also trigger the Blathers dialogue start, and he’ll just say all his phrases at once. The point of it is to introduce the user to the features of the game and give a small instruction. After that is done, the Critterpedia button would activate, so the user can interact with it and visit the Critterpedia. That is the plan for now, and if circumstances permit, the ray casting feature will also be added, with the possibility to immerse further into the experience. 

# What are the next steps? 

All that I have left is to manage the actual Critterpedia, so it showcases the critters correctly in the library, as well as provides interaction. Right now this is the UI I am going for:

![Screenshot_9](https://github.com/user-attachments/assets/5ad58467-6fd8-42d6-abd3-3449dfa628dc)
![Screenshot_5](https://github.com/user-attachments/assets/d93dbbd1-3a01-4d05-a1c7-54880e4a2dff)

The difficult part is the implementation, which I already talked about. After that I will give it a shot at implementing raycasting, which would allow the user to display models around them on IRL objects, and interact with them. 

