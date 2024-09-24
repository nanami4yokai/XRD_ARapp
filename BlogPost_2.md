# BlogPost 2 - Lab 1 - AR Project presentation

The second Blogpost is done to document the confirmed idea, as well as the beginning of the development process. 

### What is the project about?

The purpose of this project is to create an AR extension of the game “Animal Crossing: New Horizons”, where kids and adults would be able to bring to life their game experience with the museum feature.

The project will include real unidentifiable cards with variations of fish/insects/fossils specimens. In the perfect scenario, the cards would include a bar/QR code that would be scanned with the phone, that would identify which exact specimen the player collected. Then, a 3D interactive image of the specimen would be shown on the screen, and an interactive dialogue window with Blathers would appear, where the player will be able to play the same scenario present in the ACNH game. The player will be able to add the specimen to the “museum”, through which they will then be able to walk and watch the full collection. 

### What will the project look like?

Ideally, there will be 3 chambers of the museum in total, but in the context of the XRD course, I chose to first create the system head-to-toe using 3 cards to collect 3 insects, with their corresponding 3D interactive models and a working UI, featuring instructions from Tom Nook and dialogues with Blathers.

### Delimitations

- There is no card game that I know of based on ACNH with the fish/insects/fossils specimens that would be useful for this project, so I will have to make them myself.
- It would be difficult to incorporate bar/QR code recognition within the time limits, so most likely a randomizer would be implemented in the software that would identify specimens in a random manner. 
- I would also need to 3D model every specimen I want to add, as well as part of the museum showcasing aquariums, trees, greenhouses, etc.

### Technologies

The technologies used in this project include an Android device (most likely tablet) from the hardware perspective, and from the software perspective, the Unity Game Engine with the ARCore template, along with Photoshop and Blender. 

### How is the process going? 

3 physical cards have been created, as well as 3 3D insect models and some pieces of display objects. They have been imported into Unity successfully. 

![Insect_Card_1 - Copy](https://github.com/user-attachments/assets/fea23267-2c56-4118-9957-0cbda368df2f)
![Screenshot_3](https://github.com/user-attachments/assets/f6cecdc8-ed64-4834-bd8e-c31d813654de)

A project has been started using Unity 6, and the beginning of the dialogue system implemented, with a DialogueManager script (with the Start(), StartDialogue(), DisplayNextSentence(), TypeSentence() - method that types out the sentence, letter by letter, during runtime - and EndDialogue() methods), mainly the instructions given by Tom Nook in the first minutes of launching the app. 

![Screenshot_1](https://github.com/user-attachments/assets/1f3f56a4-4492-479b-8a45-81a32547a1e6)
![bandicam2024-09-2419-54-45-721-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/f4448771-5057-44df-81a3-2c9f51965317)

The card scanning and storing features are to follow, since it is needed to progress through the experience. The player would scan the cards with their Android device, and collect the assigned specimens, getting a 3D interactive model of the specimen and storing it into the Critterpedia. That would help with Museum management and the dialogues with Blathers.  
