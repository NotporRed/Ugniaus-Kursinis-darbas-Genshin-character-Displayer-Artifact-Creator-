# Genshin character displayer and Artifact creator

## What is this program?

This is a Genshin Impact character info displayer with an extra random artifact creator.  
It's main purpose is to help you see your characters information at diffrent levels and ascensions. 

## How to use?

To start all you just need to do is to run the _main.py_ file  

1. When the progam has started you will be able to select the character that you want to choose ***(currently characters go up to version 4.5)***
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/17b2220a-3346-4164-a06b-27720bc4bdb4)

3. To find a character you want:
   * Press arrows on either sides to cycle through the list.
   * Type their name, this will filter the list. (**spaces included!**)
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/9ac5dd89-10e3-4a03-b183-9de8e4496965)

4. Pressing their name will open up the sellection sceen, if you want to change character, press *del* key on your keyboard.
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/75711291-ae9c-4bee-aaf4-b0d220b054d1)

   * Top buttons set to everything to maximum or minimum. The two buttons in the middle change characrters ascention.
   * bottom four buttons level up/down the character going from -10, -1, +1, 10.
   * Pressing the **"Change Weapon"** button will lead you to a similar selection, but this time with weapons. (***weapons are automaticly level 90***)
   * Buttons labeled 1 - 5 will generate a random artifact in that slot(***they are level 20 with average substats)
   * **"Save"** button will save artifacts into *Artifacts.txt* (***The file can save multiple times but it will only see the first one, to save a new set erase the old one!***)
   * **"Load"** will load the first set of artifacts that you saved (***In the file you can enter your own substats but be careful as the syntax doesn't fully match the games***)

## Body/Analysis 

The code is written in python using OOP principles.

### The for pillars of OOP can be found here:

#### Polymorphism

- As we can see there's one button class that creates all the buttons around the file.  
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/aef4b7ef-f919-4e4a-b05b-2cc640821af5)

- However the buttons commit different functions beacause they are created using different veriable.  
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/495f2ab6-7b0b-4a40-804b-e9a12d9e59dd)

- That means their click function becomes seperate even if they are created from the same class.  
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/0bfd2da6-02f9-4366-85ba-fb56e65b0d69)


#### Abstraction and Inheritances

- We can see that in this scenario class loder is an abstract class with three methods  
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/e0e57036-81cd-4f5c-bdbc-ea831bd93778)

- Since all three classes are children of Loader they inherit the classes and overide them if they use it
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/c1bf4e43-cc89-44ad-8dd9-38fd09e5c761)

  
### Design Patterns

#### Factory

- Since I needed to generate 5 artifacts I created a factory that would do that job  
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/f33034aa-1aa7-431b-b624-003f5769826d)

- It calls to artifact class to do generate it  
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/debbf848-c667-437e-ba0e-1918c6030217)

- This makes it so I would only need to call factory with the position without any trouble  
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/394a7a5c-72de-4d40-b280-e5ab29cb593f)


#### Decorator

- From the start there was an issue with the program constantly reading file even though it didn't need to, thats why I created this decorator:
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/e906cf52-0ec2-4329-a82e-ce60c681779d)

- whith this decorator on all three classes that have can read excel first check if they already read the file
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/00955a01-2376-4228-8828-2edfeb2341fa)


### Reading & Writting to File

- reading is mainly done from excel files  
![image](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/c3050c30-4f53-4142-b402-e3e80aaac6dc)


- writing is only done with artifacts  
![Writting](https://github.com/NotporRed/Ugniaus-Kursinis-darbas-Genshin-character-Displayer-Artifact-Creator-/assets/167587196/1d182634-897b-4123-a4aa-7753d5325a47)


## Results and Summary

- One of the most difficult tasks I had was transferring data to the program.  
Since the start I thought of using Excel files however I did not expect it to be such a hasle.
From bad reading to cutting down the scope of the project because of the complexity most problems are related with excel.
However for what is used right now I believe that it's one of the most optimised parts, since I had to redo and fix it multiple times.

- One of the proudest parts for me is the character/weapon selector, I knew going in that just a simple left to right buttons wont do because of the massive list.
For this reason I am very delighted by the results of the search.

- The character stat display screen even if not pretty works well and displays stats that sometimes are annoying to find online and even if the artifacts are not fully correct they give you a nice picture of your characters build + can let you see if your character meets the requirements set by [KQM](https://keqingmains.com).

## Conclusion

In this project I not only learned how to impliment OOP knowledge into a program, but also how to read and write into excel files, work with py games to create a "game". Even if results didn't fully reach my expectations I am motivated to someday try and make it better or to create something completely new.



