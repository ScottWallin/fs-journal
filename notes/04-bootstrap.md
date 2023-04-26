# Bootstrap

NOTES FOR WEDNESDAY APRIL 26

* cmd + / is the notes hotkey.
* <i> is for icons. 
* MDI works as classes. Do mdi mdi-x to grab the desired icon.

Containers, rows, & columns are the three things that make up its grid.
css-tricks.com is a good resource to help too.
justify-content and align-items are similar but different.
justify-content works on x axis
align-items works on y axis
* Mobile First Design * easier to start small, then go bigger, than go bigger and condense it.
Each row has 12 units across the breadth that we can use.
* Use bootstrap as a tool for scaffolding how much space you want things to take up.
* col-x determines how many columns will take up a row.

* find the CDN on the bootstrap website to bring over the catalog of things it uses.
Make sure you link in the bootstrap before the style.css. Order matters.

* for each container you make, be sure to do a class="container" or class="container-fluid" depending on which is needed. Differences below.
Container-fluid leaves no margin. It's rare that simply "container" will be used. "Container" contains too much margin. "Container" is used more when you want to leave a margin, but not have to worry about designing it.

* .row makes <div class="row"> automatically. adding .row*x adds x number of rows.
anything using the ROW class, make it a section, not a div.
.col-6*2 then tab draws both 6 columns in the row.
<style> snippet brings in some bootstrap designs that help out.
class="col-12 col-md-4" defaults to a col 12, and on medium screen and larger, become a col 4.
class="img-fluid" is a bootstrap element that doesn't let the image get any larger than the column it's inside of.
.col without a -x defaults to a col-12.

* bootstrap has a class for margins called "mx-x" and each number of x goes up by .5em.
it also has "mb-" for margin bottom.
class="sticky-top" goes in the header and makes it so whatever tag this is placed in, stays on the screen while you scroll the whole time.
images and text are considered inline block elements.
"p-x" gives a value for padding all around.
"rounded" rounds out the corners but it does have a default.
"rounded-x" adjusts the borders to your preferences.
"text-center" works on buttons, images, text, anything classified as an inline.
Padding in the row, adds padding just to the row itself. The elements inside the row still need to have their own padding added.
"fw-x" = font weight to bold the text. x = bold, light, etc.

* with buttons, doing "text-center" on the button tag will only center the text. Doing it on the parent tag instead will center the button itself. Or place the button in whatever position is desired.

* icons (<i>) follow sizing with font sizing. So f1-6 with 1 being the biggest and 6 being the smallest.

* class="debug" adds the boxes for seeing containers/rows/columns to see where things are placed.




