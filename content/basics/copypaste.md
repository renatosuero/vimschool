+++
title = "Copy & Paste"
date =  2018-02-03T13:25:00-00:00
weight = 9
+++

Sometimes I hear this question "Why do you use Vim?"(Renato). I just ask "how do you delete one line in your editor" and my answer is: I just type **dd** and I complete... I didn't need to leave my hands from the keyboard.  

First, we learn how we can *copy* contents. The key used is **y**(yank), but it alone doesn't do anything, we need to use other keys(do you remember those keys for navigating?). Let's see any combinations:   

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
| **xp**  | Transpose to letters             |
| **D**   | Delete to end of line            |

You can change **d** by **c**, the difference is that **c** cut and change the mode for the insert. Just any differences using c.  

|Key      | Description                  |
|---------|------------------------------|
| **s**   | Delete char under the cursor |
| **S**   | Delete line under the cursor |

We show any options to help you start to use it, you can do a lot of combinations/repetitions. Try to do something that you don't see here and tell us.

------------

> Quick tip: Use combinations/repetitions, it'll give you a amazing productivity.

