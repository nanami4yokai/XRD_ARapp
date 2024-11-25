# BlogPost 8 - Additional - AR Project additional update

This blog post is intended for explaining the final updates done to the AR project and sum it all up. I would’ve stuck to the original plan of 7 BPs, but I had to change a whole lot of the original implementation concept, so I decided to record it too.

So, the concept I am talking about is the use of Scriptable Objects in the project. In BP 7 I described how I would use SOs for storing critters inside the Critterpedia, which is the same strategy I used during the GMD course when I had to implement the inventory system. Later, when I got to the actual Critterpedia implementation, I noticed that it was a big mistake of not using SOs from the beginning, that would unite all the critters’ related assets and data. Therefore, I had to change the functionality implementation a bit in order to accommodate the new concept. 

![Screenshot_15](https://github.com/user-attachments/assets/d61f2057-7585-41ba-8933-2a3e8c561219)

Even though not entirely, since that would’ve taken a lot of time, I used roundabouts. 

For example, card recognition:

![Screenshot_14](https://github.com/user-attachments/assets/7d3b1bca-5542-406d-b38e-ae4b069374f9)

I used dictionaries to reference cards to models:

![Screenshot_11](https://github.com/user-attachments/assets/113d8512-b544-4d93-892b-ca47db41f4ec)
![Screenshot_12](https://github.com/user-attachments/assets/232c45f1-045b-4cf9-b562-6134f1a8ccff)
![Screenshot_13](https://github.com/user-attachments/assets/f6ba78ab-0f06-4592-8358-008b57ea447e)

![Screenshot_10](https://github.com/user-attachments/assets/67d7326b-ae0e-4d6f-95f3-f7664e74a719)

Since I implemented functionality of recognising critters by name, it would mean that every naming related to a critter should’ve been the same, and the dictionary helped me omit changing the name of the Scriptable Objects and map out the references. 

Overall, I encountered a bunch of issues, I struggled to implement recognition and addition to Critterpedia a lot. This is what the Equals() and GetHashCode() methods are for in the Critter class, which were to constantly check and make sure that the same entity (meaning a certain critter) is traveling through all the stages of the game - recognising the card, showing the collected Critter image, adding it to the Critterpedia and sending the data to it, attaching the Critter’s logo to a slot in the Critterpedia and also displaying the correct info card. You can see a bunch of debug logs throughout the whole code because I needed to keep checking every step of the implementation and figure out 100% what is wrong.  

The conclusion would be that next time I would need to come up with a solid implementation strategy before the very start. The AR base features I used to create the project is image recognition and raycasting (for showcasing models on the card).

Generally speaking, the AR project proved to be difficult to implement and I had a lot more planned, but because of different struggles I encountered, as well as the time limit, I had to drop a lot from the original concept, which I am very disappointed with. 

Anyway, below you can see 2 videos showcasing the final product. First is using the custom testing script I used throughout the majority of the development process, and second is the final build used on my Android device. 

Enjoy!

[AR project Test mode](https://youtu.be/3RxcKOCBKRY)

[AR project final build](https://youtu.be/_zNiUK8opEI)
