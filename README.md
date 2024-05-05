# Genshin character displayer and Artifact creator

## What is this program?

This is a Genshin Impact character info displayer with an extra random artifact creator.  
It's main purpose is to help you see your characters information at diffrent levels and ascensions. 

## How to use?

To start all you just need to do is to run the _main.py_ file  

1. When the progam has started you will be able to select the character that you want to choose ***(currently characters go up to version 4.5)***
![Main screen](https://media.discordapp.net/attachments/790862943239405589/1236677299156553870/image.png?ex=6638e0fc&is=66378f7c&hm=459f245b3db486b54bd1bcdb51ac2e783161ea5aaffcf76e66e0b98d8ecc671d&=&format=webp&quality=lossless)
2. To find a character you want:
   * Press arrows on either sides to cycle through the list.
   * Type their name, this will filter the list. (**spaces included!**)
![Searching for characters](https://media.discordapp.net/attachments/790862943239405589/1236678351310290985/image.png?ex=6638e1f7&is=66379077&hm=00d543c8656924d796017a0f4987d5b3590cceaea4742b3d89b9c170a56a8bd6&=&format=webp&quality=lossless)
3. Pressing their name will open up the sellection sceen, if you want to change character, press *del* key on your keyboard.
![Character screen](https://media.discordapp.net/attachments/790862943239405589/1236679251869040640/image.png?ex=6638e2ce&is=6637914e&hm=b0b445fa78dcce246ff30f2cf966eddc88eb344e965dfe8902c7278b43b29893&=&format=webp&quality=lossless)
   * Top buttons set to everything to maximum or minimum. The two buttons in the middle change characrters ascention.
   * bottom four buttons level up/down the character going from -10, -1, +1, 10.
   * Pressing the **"Change Weapon"** button will lead you to a similar selection, but this time with weapons. (***weapons are automaticly level 90***)
   * Buttons labeled 1 - 5 will generate a random artifact in that slot(***they are level 20 with average substats)
   * **"Save"** button will save artifacts into *Artifacts.txt* (***The file can save multiple times but it will only see the first one, to save a new set erase the old one!***)
   * **"Load"** will load the first set of artifacts that you saved (***In the file you can enter your own substats but be careful as the syntax doesn't fully match the games***)

## Body/Analysis 

The code is written in python using OOP principals.

### The for pillars of OOP can be found here:

#### Polymorphism
- As we can see there's one button class that creates all the buttons around the file.  
![Button Class](https://media.discordapp.net/attachments/790862943239405589/1236686949075521547/image.png?ex=6638e9f9&is=66379879&hm=3acffb3248fa9cad3cef1e1c3afad0515e4c7f99970812a6851b066f0f5c5347&=&format=webp&quality=lossless)
- However the buttons commit different functions beacause they are created using different veriable.  
![Two Buttons](https://cdn.discordapp.com/attachments/790862943239405589/1236687776699908210/image.png?ex=6638eabe&is=6637993e&hm=1edd44e5b221340fc57cd63a9edde084b3ac6b018c58a48691bf7d5dc0e955c0&)
- That means their click function becomes seperate even if they are created from the same class.  
![Buttons Calling](https://cdn.discordapp.com/attachments/790862943239405589/1236688614214074439/image.png?ex=6638eb86&is=66379a06&hm=284cf6250196a9b5b0df2c85cc453ec1c666afd9ba0392a69d1c174f300a4fc7&)

#### Abstraction and Inheritances
- We can see that in this scenario class loder is an abstract class with three methods  
  ![Loader Class](https://cdn.discordapp.com/attachments/790862943239405589/1236691372711608331/image.png?ex=6638ee17&is=66379c97&hm=d1ba24c0520853f39394434041f39b54866bca6af7a643d6314ca615836a6aca&)
- Since all three classes are children of Loader they inherit the classes and overide them if they use it
  ![Loader Children](https://cdn.discordapp.com/attachments/790862943239405589/1236692990047555636/image.png?ex=6638ef99&is=66379e19&hm=af1283445bbaca1f82032ea3f99dc593c46d4b5bb357f0cd2806a9b800c600a1&)
  
### Design Patterns

#### Factory
- Since I needed to generate 5 artifacts I created a factory that would do that job  
![Factory](https://cdn.discordapp.com/attachments/790862943239405589/1236696069992349736/image.png?ex=6638f277&is=6637a0f7&hm=16cc956d0f75ef498bbb6c334e0c5b97950a6959621e90bea2dc4494735db716&)
- It calls to artifact class to do generate it  
![Artifact](https://cdn.discordapp.com/attachments/790862943239405589/1236696397622022234/image.png?ex=6638f2c5&is=6637a145&hm=28db39204b62017982e9731159d8a818da5583c05eb56d526c6d23f5fdaf00ac&)
- This makes it so I would only need to call factory with the position without any trouble  
![Generating Artifact](https://cdn.discordapp.com/attachments/790862943239405589/1236696920160862380/image.png?ex=6638f342&is=6637a1c2&hm=0e199187fe58fe365859f97e3dc96b3f7cf15459b4b2ebc35592b990941ec61f&)

#### Decorator
- From the start there was an issue with the program constantly reading file even though it didn't need to, thats why I created this decorator:
![Decorator](https://cdn.discordapp.com/attachments/790862943239405589/1236697624669720720/image.png?ex=6638f3ea&is=6637a26a&hm=f45a621ab685ced73cd1a96b01ac156dc6b7395668ea508557c6bd559ffae47d&)
- whith this decorator on all three classes that have can read excel first check if they already read the file
![Decorator in use](https://cdn.discordapp.com/attachments/790862943239405589/1236697665056800939/image.png?ex=6638f3f4&is=6637a274&hm=0fbb7bd6636a5fcd92de471e0ca835b23da6416a764231e9112480e30762ef77&)

## Results and Summary

- One of the most difficult tasks I had was transferring data to the program.  
Since the start I thought of using Excel files however I did not expect it to be such a hasle.
From bad reading to cutting down the scope of the project because of the complexity most problems are related with excel.
However for what is used right now I believe that it's one of the most optimised parts, since I had to redo and fix it multiple times.

- One of the proudest parts for me is the character/weapon selector, I knew going in that just a simple left to right buttons wont do because of the massive list.
For this reason I am very delighted by the results of the search.

- The character stat display screen even if not pretty works well and displays stats that sometimes are annoying to find online and even if the artifacts are not fully correct they give you a nice picture of your characters build + can let you see if your character meets the requirements set by [KQM](https://keqingmains.com).

## Conclussion

In this project I not only learned how to impliment OOP knowledge into a program, but also how to read and write into excel files, work with py games to create a "game". Even if results didn't fully reach my expectations I am motivated to someday try and make it better or to create something completely new.



