+++
title = "Navigating Extended"
date =  2018-02-03T10:32:00-00:00
weight = 7
+++
We have a lot of possibilities/keys to move into the files without we need to use the mouse. Because these keys and combinations that we don't leave our hands from the keyboard.  
We'll divide it into some parts, just to facilitate the structure.

## Screen or File
When we are working in big files, sometimes we are writing in the bottom of the screen. Vim has a solution for us =). Now we'll know the keys to move the screen.  

 Key      | Description                                       |
|---------|---------------------------------------------------|
| **zt**  | Move the screen to the top of the window          |
| **zz**  | Move the screen to the middle of the window       |
| **zb**  | Move the screen to the bottom of the window       |


Let's think, how many times we open a file and see that we need to change the last lines, but the editor opens in the first line. For us Vim users this isn't a problem, because we have some keys to help us.  

 Key     | Description                                       |
|--------|---------------------------------------------------|
| **H**  | Move the cursor to the highest line on the screen |
| **M**  | Move the cursor to the middle line on the screen  |
| **L**  | Move the cursor to the lowest line on the screen  |


When we know that we want to go to begin/end of the file, we can use these keys.  

 Key      | Description                          |
|---------|--------------------------------------|
| **gg**  | Move the cursor to the begin of file |
| **G**   | Move the cursor to the end of file   |

When you know the line that we need to go, we just need type the number and **G**, we have another option for this. We can type **:** and the number(just remember, : it works in normal mode). The difference here is, using <number line>G you can do it in visual mode to select texts.

 Key      | Description              |
|---------|--------------------------|
| **``**  | Return to the previous place |
| **''**  | Return to previous line  |

> These commands will have different behavior when you execute in big or small files. I suggest that you open some small and big files, then test it to understand.


## Words or content
Now let's see keys to navigate between words, these keys help us to move fast and mainly we don't need to use the mouse.  

Let's start with navigation into the line.  

| Key     | Description                      |
|---------|----------------------------------|
| **^**   | Move to first char in begin line |
| **0**   | Move to begin line               |
| **$**   | Move to end line                 |


Then let's navigate between words.  

| Key      | Description                    |
|----------|--------------------------------|
| **w**    | Move to begin with next word     |
| **e**    | Move to end of current word    |
| **b**    | Move to begin with the previous word |
| **ge**   | Move to end of the previous word   |

Now we will show a great way to jump into the words. We can use the keys **f** or **t** to do it.  
For example, in this line we type *ff*, the cursor will jump to the first occurrence that it finds (exactly in the char found). If we use *tf*, the behavior is almost equal, but now, the cursor will be before the char found(if you see this markdown, the cursor will be exactly in * before the first *f* found).    

| Key       | Description                                  |
|-----------|----------------------------------------------|
| **fc**    | Jump to next char found                      |
| **Fc**    | Jump to previous char found                  |
| **tc**    | Jump to next char found(go to previous char) |
| **Tc**    | Jump to previous found (go to next char)     |

Ok this is nice, but sometimes we need to repeat it, how can we do it?  

| Key      | Description                  |
|----------|------------------------------|
| **;**    | Jump to next char found      |
| **,**    | Jump to previous char found |

We can jump using a word, and we can do it.  

| Key      | Description                  |
|----------|------------------------------|
| **\***   | Jump to next word found      |
| **#**    | Jump to the previous word found |


------------

> Just remember: You can use numbers to define repetitions. For example, you want to jump word and you use **w** you can do **2w** to jump to the second occurrence found.    
