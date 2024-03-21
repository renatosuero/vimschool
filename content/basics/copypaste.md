+++
title = "Copy & Paste"
date =  2018-02-03T13:25:00-00:00
weight = 9
+++

Sometimes I hear this question "Why do you use Vim?" (Renato). I just ask, "How do you delete one line in your editor?" My answer is: I just type **dd** and it's gone... I didn't need to move my hands from the keyboard.  

First, we learn how we can *copy* contents. The key used is **y**(yank), but it alone doesn't do anything, we need to use other keys (do you remember those keys for navigating?). Let's see some combinations:   

|Key            | Description                       |
|---------------|-----------------------------------|
| **y space**   | Yank char under the cursor        |
| **yy**        | Yank the line under the cursor    |
| **2yy**       | Yank the 2 lines under the cursor |
| **yw**        | Yank word                         |
| **y$**        | Yank to end of line               |

So, how do we paste the content?  

|Key      | Description             |
|---------|-------------------------|
| **p**   | Paste after the cursor  |
| **P**   | Paste before the cursor |


Now, we will see how **cut** content, as you can copy using movements and repetitions, you can do the same to cut too.   

|Key      | Description                      |
|---------|----------------------------------|
| **dd**  | Delete the line under the cursor |
| **dw**  | Delete the word                  |
| **x**   | Delete current char              |
| **X**   | Delete previous char             |
| **xp**  | Transpose two letters (see why?) |
| **D**   | Delete to end of line            |

You can change **d** to **c**, they both cut the text, but **c** then switches to insert mode ready to type new text. Make changes using c.  

|Key      | Description                                         |
|---------|-----------------------------------------------------|
| **s**   | Delete char under the cursor, switch to insert mode |
| **S**   | Delete line under the cursor, switch to insert mode |

We show any options to help you start to use it, you can do a lot of combinations/repetitions. Try to do something that you don't see here and tell us.

------------

> Quick tip: Use combinations/repetitions, it'll give you amazing productivity.

