# Vim School

This is the project page for the `Vim School` website.

You can see it online at: (https://www.vimschool.com)[https://www.vimschool.com]

This project was born out of the excitment and willingness to share knowledge about Vim by two long time users: [Renato Suero](https://github.com/renatosuero) and [Ricardo Gerardi](https://github.com/rgerardi).


## Running it locally

If you want ot run the website locally on your machine, you need [Hugo](https://gohugo.io/) minimum version `0.25` and the [Hugo Learn Theme](https://github.com/matcornic/hugo-theme-learn). This theme is provided as a `git submodule` of the main repo.

After clonning the repo into a local directory, change to that directory and run the following commands:
```
git submodule init
git submodule update
```
Git will clone the theme in the correct directory. Now start a local hugo server and enjoy !
```
hugo server
```
By default the server will run on [http://localhost:1313](http://localhost:1313)
