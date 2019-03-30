# Basic Grid 1.0

Basic Grid is a simple customizable CSS grid framework inspired by Bootstrap, but created from scratch. It’s what I loved about Bootstrap with a few additions, and yet much of what I never used removed.

If you like and want to use this system, I also have a responsive header navigation that sizes into a CSS-only hamburger menu. You can check it out [here](https://github.com/amportfolio/css-dropDown-menu-1).

I’m also using [Normalize](https://github.com/necolas/normalize.css) and [Eric Meyer’s reset](http://meyerweb.com/eric/tools/css/reset/) for improved cross-browser rendering. If you wish to remove this or use your own reset system, see *Customizing Basic Grid* at the bottom on how you can process your own customized version of this framework.

## Getting Started

Beyond the standards of HTML like declaring doctype, you will need to set your viewport in order to make this work perfectly:

`<meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0">`

## Containers

Like Bootstrap, you will need to declare a container before you can set up rows and grid areas. You cannot nest the container, but more use them at the first level.

You have two options for containers. You can have fixed width responsive containers that stay fixed to the width of the set grid:

    <div class="container">
        ...
    </div>

You can also have containers that stretch to a width of 100% and fluidly size itself with your viewport:

    <div class="container-fluid">
        ···
    </div>


## Grid Column Options

One major difference with this system versus Bootstrap is the addition of three additional breakpoints. You can see how things break down here:

Breakpoint | Size Range | Ideal For
------------ | ------------- | -------------
`.col-xxs-` | 1px–319px | Small Smartphones
`.col-xs-` | 320px–479px | Normal Smartphones
`.col-sm-` | 480px–767px | Phablets and Landscape Orientation
`.col-md-` | 768px–991px | Small Tablets
`.col-lg-` | 992px–1199px | Large Tablets and Small Laptops
`.col-xl-` | 1200px–1439px | Large Laptops and Workstation Monitors
`.col-xxl-` | 1440px+ | Large Screens

## Setting up rows

Like Bootstrap, you’ll need to set up rows first before dropping in individual divs as your grid areas. Follow this syntax and you're good to go:

    <div class="container-fluid">
        <div class="row">
            ···
        </div>
    </div>

From there, you just simply set up your grid areas using `.col-` with the breakpoint and the number of columns you wish to use. Refer to index.html to see examples.

## Column Wrapping

If you happen to set up grid areas that go past your designated number of columns *(12 is the default)*, things will just wrap to the next line.

## Column Reset

You can also control the wrapping by using a separate div with the `.clearfix` class. This will build “rows within the rows” in so many ways. You can also make those clearfix divs appear and disappear in certain cases with the `.hidden` and `.visible` classes, which I’ll get into later.

## Nested Columns

If you wish to nest columns within a column, you simply set up a new `.row` and go from there. The grid area you’re in will act as a container for the new row.

## Column Reordering with Push/Pull

You can reorder the placement of columns using `push-` and `pull-` classes in addition to your grid column classes. Your format will be `.col-` with `push-` or `pull-`, the breakpoint you’re aiming for, and the number of columns you’re pushing or pulling.

You should have all pushes and pulls equal the total number of columns as you see in the example below. If you wish to create spaces, then use the `offset-` class further down.

## Column Offset

If you wish to set up grid areas to sit in certain columns, then use the `offset-` class in addition to your grid column class. Simply start with `.col-` and `offset-`, then the breakpoint you’re aiming for, and the number of columns you wish to offset the area.

Please bear in mind if you set up an offset where the grid area goes beyond he total number of columns *(12 is the default)*, then your grid area will wrap to the next line.

## Column Visibility

You can make grid areas appear and disappear at certain breakpoints by using `.hidden-` and `.visible-` classes alongside your grid column classes. Simply use `.hidden-` or `.visible-` with the breakpoint you wish.

**NOTE:** It seems when you want to hide a grid area on one breakpoint, you need to declare the `.visible-` class on the other remaining breakpoints you wish this area to appear. It’s a bug I also noticed with Bootstrap and am exploring a workaround.

## Customizing Basic Grid
An additional benefit to this CSS framework is you can totally customize the number of breakpoints you want, the widths of those breakpoints, their names, the gutter, and the total number of columns you want.

I’ve included the SCSS files used to make the full grid. Simply open *_config.scss* and change the configuration as you see fit, then process it into finished CSS using a preprocessor such as Gulp or Koala.

## Questions? Comments? Suggestions?

Please feel free to reach out or fork this and improve on it.

## Authors

* **Alex Moschopoulos** - *Initial work* - [amportfolio](https://github.com/amportfolio)

## Acknowledgments

* Bootstrap...it was a nice start, but it drove me to push for more.
* SCSS...I love it