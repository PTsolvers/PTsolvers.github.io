# website-memo
This document lists the basics on how to edit the PTsolvers website accessible at https://ptsolvers.github.io.

🚧 More to come soon.

## Franklin static website

To test the website locally (or after making the a pull from Git):
```julia-repl
julia> using Franklin, NodeJS

julia> serve(clear=true)
```
> Note the first time you are using `NodeJS`, you need to execute:
```julia-repl
julia> run(`sudo $(npm_cmd()) install highlight.js`)
```

## How-to

### Add YouTube video
To embed YouTube videos, go to YouTube, click on the `Share` link and then `<Embed>`, and copy-paste the script into an html block:
```md
~~~
<iframe width="560" height="315" src="https://www.youtube.com/embed/DvlM0w6lYEY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
~~~
```

### gif and loopcount

You can use [gifsicle](https://www.lcdf.org/gifsicle/) as command line tool to modify the loopcount for gifs to be included in the scripts (tested on MacOS):
```sh
gifsicle gif_loopcount_inf.gif --no-loopcount > new_gif_no_loopcount.gif
gifsicle gif_loopcount_inf.gif --loop=3 > new_gif_loopcount_3.gif
```

## Misc

### Control the global page content width

Put in `_layout/head` the following, before the opening of the body and after the loading of the css:
```html
<style>
.content {max-width: 50rem}
</style>
```
