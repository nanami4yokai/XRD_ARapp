# BlogPost 3 - Lab 2 - Updates

This Blogpost describes the updates done on the project, as well as details about the project execution and plans on the next steps.

### How is the process going? 

The implementation of the AR features proved to be very time consuming: every minor change must be tested, but building the app every time to the android device got annoying really bad really fast. Unfortunately, any 3rd party AR Simulators from the Unity Store are pretty expensive, so the only way to test is the back and forth development and build. 

To save up some time and exclude potential issues with the Android device, I built some test UI that would make it easy to test implementation updates directly inside Unity. More on that later. 

### What has been implemented so far? 

The card scanning feature has been implemented, though not without problems - since I used the same reference image for multiple 3D models, it proved to be quite difficult to make it work right, so that the app would throw different models each time using the randomizer (for the sake of the demo of the project, it would be necessary to get 3 different models), even to recognize the image was troublesome.

https://github.com/user-attachments/assets/be0bedb5-b49f-4c45-9c7a-c582554110bc

Due to this, I decided to change the cards and make each of them different and mock up a QR code recognition system.

![Insect_Card_Peacock_1](https://github.com/user-attachments/assets/7541056b-d4ab-4fa8-8b6e-a9ef32c7c467)
![Insect_Card_Monarch_1](https://github.com/user-attachments/assets/94dd8c1b-84a3-448d-8569-aa9191a7e552)
![Insect_Card_Emperor_1](https://github.com/user-attachments/assets/544757de-e038-499e-bedd-47cc68c2bfc7)

After that, things got easier. I started work on animations and interactivity. Now, after identifying a critter, the app would show some animations and the image of the critter collected, as well as 2 buttons, which the user can interact with and add the critter to the Criterpedia, or skip the critter and return to the home screen. 

https://github.com/user-attachments/assets/b0a6e620-c70b-4a06-bddb-3e5f3fdda62d

To make life easier, I also implemented some test UI, which I talked about before. 

![photo_2_2024-10-06_20-19-19](https://github.com/user-attachments/assets/ea046cfa-50b1-4ed2-96b3-650846b177aa)

It would operate with the CritterCollectingManager to identify when a critter would be found, without actually using the Android camera and scan images. 

![photo_1_2024-10-06_20-19-19](https://github.com/user-attachments/assets/66d9f237-57f5-4a7b-9d70-7f3df9478c82)
![photo_3_2024-10-06_20-19-19](https://github.com/user-attachments/assets/e5f6b86a-39f6-414c-b1ad-b7088d28ce31)

https://github.com/user-attachments/assets/d524aecb-4ffc-4166-8723-ef4e10949cea

I encountered unexpected difficulties with implementing animations and making them work right (so please ignore the obvious bug in the video above). This, plus some other minor issues I tried to take care of, slowed down the process, therefore I am not sure if I will manage to implement the whole concept until the deadline. 

### What are the next steps? 

Next, I would like to fix the issues with my animations, since the infinite loop they go through impedes me from interacting with the app anymore. After that, next would be to implement the Critterpedia. For that, I would need to  finalize the conversation with Tom Nook and introduce the next NPC - Blathers, that would instruct the user on what to do further, and create the UI elements for the actual pedia, as well as the minimal interaction features needed for a more or less full experience. 
