# Redshift for Awesome WM

This is a tiny Lua library to interface the [Awesome window manager](http://awesome.naquadah.org) with [redshift](http://jonls.dk/redshift/), a program that dims the screen to make it easier on your eyes, especially at night.

What makes this any more useful than *gtk-redshift*, you might ask? Well, it offers the following features:

* _Integration with awesome via lua wrapper functions._ Toggling redshift with a keyboard shortcut? Automatically undimming the screen when launching the photo editor? Now anything is possible.
* _Support for multiple monitor setups that don't use xrandr._ If you're multiheading graphics cards, this is a must-have.
* _Automatic, periodic brightness adjustments._ (Well, redshift offers this out of the box, but I thought it was worth mentioning the library takes care of this for you.)

When designing this library, I followed the KISS principle. I wrote convenient wrapper functions to do the dirty work for you. It's up to *you* to program your own keybindings, bells, and whistles.

## Install

In your awesome configuration directory:

`git clone git://github.com/YoRyan/awesome-redshift.git redshift`

In your rc.lua:
`local redshift = require("redshift")`
`
-- set binary path (optional)
redshift.redshift = "/usr/bin/redshift"
-- set additional redshift arguments (optional)
redshift.options = "-c ~/.config/redshift.conf"
-- 1 for dim, 0 for not dimmed
redshift.init(1)
`

## Usage

Done! Now you have these functions at your disposal:

* redshift.dim()
* redshift.undim()
* redshift.toggle()

(They're pretty self-explanatory...)