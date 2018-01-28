+++
title = "Navigating Extended"
date =  2017-10-30T10:09:28-04:00
weight = 7
+++
We have a lot of possibilities/keys to move into the files without need to use mouse. Because these keys and combinations that we don't leave our hands from keyboard.  
We'll divide it in some parts, just to facilitate the structure.

##Screen or File
When we are working in big files, sometimes we are writing in the bottom of the screen. Vim has a solution for us =). Now we'll know the keys to move the screen.  

 Key      | Description                                       |
|---------|---------------------------------------------------|
| **zt**  | Move the screen to the top of the window          |
| **zz**  | Move the screen to the middle of the window       |
| **zb**  | Move the screen to the bottom of the window       |


Let's think, how many times we open a file and see that we need to change the last lines, but the editor open in the first line. For us Vim users this isn't a problem, because we have some keys to help us.  

 Key     | Description                                       |
|--------|---------------------------------------------------|
| **H**  | Move the cursor to the highest line on the screen |
| **M**  | Move the cursor to the middle line on the screen  |
| **L**  | Move the cursor to the lowest line on the screen  |


When we know that we want to go to begin/end of file, we can use these keys.  

 Key      | Description                          |
|---------|--------------------------------------|
| **gg**  | Move the cursor to the begin of file |
| **G**   | Move the cursor to the end of file   |

When you know the line that we need to go, we just need type the number and **G**, we have another option for this. We can type **:** and the number(just remember, : it works in normal mode). The difference here is, using <number line>G you can do it in visual mode to select texts.

 Key      | Description              |
|---------|--------------------------|
| **``**  | Return to previous place |
| **''**  | Return to previous line  |

> These commands will have different behavior when you execute in big or small files. I suggest that you open some small and big files, then test it to understand.


##Words or content

keys
w,e,b
f,t
0,^,$

###Miscellaneous
gv to show the last selection
