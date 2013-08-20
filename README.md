# Quickdraw

An awesome SASS tool for building fixed or responsive grids on the fly.  If you're
familiar with the 960 Grid or Skeleton, you are familiar with Quickdraw.

* Developed By: [https://twitter.com/sethenmaleno](@sethenmaleno)
* Built with: [http://sass-lang.com/](http://sass-lang.com/)
* Inspired by: [http://www.getskeleton.com/](http://www.getskeleton.com/) & [http://960.gs/](http://960.gs/)

## What is Quickdraw?

Quickdraw was born out of necessity.  While doing front end work, developers may find themselves
in a position where they need to create a different grid for different projects.  Changing all of 
these values by hand in CSS can become a tedious and possibly frustrating task.
Quickdraw's goal is to take all of the headache out for you by dynamically generating
the CSS you need via SASS to get the grid laid out in seconds.

Quickdraw uses a combination of media queries and percentages to deliver a great mobile experience
no matter what device someone is viewing your project on.  When generating a fixed grid, Quickdraw
uses the same math that is used at [http://960.gs/](http://960.gs/).

With that in mind, Quickdraw was built for developers who want to have the flexibility of 
making any sort of grid they can imagine on the fly without having to change much (we all know how
fickle designers can be).

## How do I use it?

Quickdraw is extremely easy to use.  Since it's built in SASS you should familiarize yourself
on the basics at [http://sass-lang.com/](http://sass-lang.com/).

Just follow these steps:

1.  Clone the repo to your local machine.
2.  Grab a copy of the `grid.scss` in the `stylesheets/sass` directory and add to your project.
3.  In your favorite shell prompt (Terminal, iTerm, etc.) change directory into your project
	and run your `sass --watch` task.  

Now, everytime you compile your `grid.scss` file, there will be a brand new CSS file for you to use based on
the variables you have given it.

## Customizing Quickdraw

The best feature about Quickdraw is it's able to make any sort of grid you want whether that's a 
responsive or fixed one.

If you open up the `grid.scss` file, you will find a few variables at the top of the file
that you are able to set to your liking.  Provided is a table that outlines all of them in order
they appear in the `grid.scss` file and what their value should be.

| Variable                      | Value(s) Should Be    | Description                                                                                              |
| ----------------------------- |:---------------------:|:--------------------------------------------------------------------------------------------------------:|
| `$baseColumns`                | integer               | Base columns for the entire project.  See [$baseColumns](#basecolumns).
| `$responsive`                 | boolean               | `true` for responsive, `false` for fixed.  See [$responsive](#responsive).
| `$gridConvention`             | string                | Naming convention for grids.  See [$gridConvention](#gridconvention).
| `$prefixConvention`           | string                | Naming convention for prefix.  See [$prefixConvention](#prefixconvention).
| `$suffixConvention`           | string                | Naming convention for suffix.  See [$suffixConvention](#suffixconvention).
| `$baseColumnWidth`            | integer               | Base column width for desktop.  See [$baseColumnWidth](#basecolumnwidth).
| `$baseGutterWidth`            | integer               | Base column gutter for desktop.  See [$baseGutterWidth](#basegutterwidth).
| `$tabletPortraitColumnWidth`  | integer               | Tablet portrait column width.  See [$tabletPortraitColumnWidth](#tabletportraitcolumnwidth).
| `$tabletPortraitGutterWidth`  | integer               | Tablet portrait column gutter width.  See [$tabletPortraitGutterWidth](#tabletportraitgutterwidth).
| `$mobilePortraitColumnWidth`  | integer(s)            | Mobile portrait column width.  See [$mobilePortraitColumnWidthh](#mobileportraitcolumnwidth).
| `$mobileLandscapeColumnWidth` | integer(s)            | Mobile portrait column gutter width.  See [$mobileLandscapeColumnWidth](#mobilelandscapecolumnwidth).


### `$baseColumns`<a id="basecolumns" /><a/>
This variable controls how many columns wide your grid actually is.  For example, you could set `12`, `16`, or even `24` if you really wanted to.  This should typically be
an even number that is easily divisible.  You can choose a odd number such as `15` or `13` but this may give you subpixels which don't cooperate well in some browers.

### `$responsive`<a id="responsive" /><a/>
This variable controls whether or not the grid compiled by Quickdraw is responsive (percentages) or fixed (pixels).  Simply passing a `true` for responsive and a `false` for fixed
does the trick.

### `$gridConvention`<a id="gridconvention" /><a/>
This variable is the naming convention for your grids.  For example, if you gave this variable a value of `myGrid_` and had a `$baseColumn` variable of `12` your compiled CSS would
have class names such as `myGrid_1, myGrid_2` all the way to `12` (or whatever your base columns are).  This is purely for convenience.  

### `$prefixConvention`<a id="prefixconvention" /><a/>
This variable is the naming convention for your prefix.  For example, if you gave this variable a value of `myPrefix_` and had a `$baseColumn` variable of `12` your compiled CSS would have class names such as `myPrefix_1, myPrefix_2` all the way to `11` (`$baseColumns` - 1).  This is purely for convenience.  This is used to add `padding` to the left of your grid.

### `$suffixConvention`<a id="suffixconvention" /><a/>
This variable is the naming convention for your suffix.  For example, if you gave this variable a value of `mySuffix_` and had a `$baseColumn` variable of `12` your compiled CSS would have class names such as `mySuffix_1, mySuffix_2` all the way to `11` (`$baseColumns` - 1).  This is purely for convenience.  This is used to add `padding` to the right of your grid.

### `$baseColumnWidth`<a id="basecolumnWidth" /><a/>
This variable controls how wide the columns are in a desktop environment. 

### `$baseGutterWidth`<a id="basegutterWidth" /><a/>
This variable controls how wide the column gutters in a desktop environment. 

### `$tabletPortraitColumnWidth`<a id="tabletportraitcolumnwidth" /><a/>
This variable controls how wide the columns are in a tablet portrait environment.

### `$tabletPortraitGutterWidth`<a id="tabletportraitgutterwidth" /><a/>
This variable controls how wide the column gutters are in a tablet portrait environment.

### `$mobilePortraitColumnWidth`<a id="mobileportraitcolumnwidth" /><a/>
This variable is actually a SASS `if` statement that you need to give 2 values.  The first value is the second argument passed to the SASS `if` which is a percentage.  This tells
Quickdraw that if the `$responsive` variable is set to `true` to use this value.  The second value is the thid argument passed to the SASS `if` which is a pixel.  This tells
Quickdraw that if the `$responsive` variable is set to `false` to use this value. 

### `$mobilePortraitColumnWidth`<a id="mobilelandscapecolumnwidth" /><a/>
This variable works exactly the same as the `$mobilePortraitColumnWidth` variable outlined above.
