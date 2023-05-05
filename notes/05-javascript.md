 # JavaScript

Monday, May 1st,

Shift + Alt/Opt copies the line.

typing "return" into a function also called short changing. return stops the function. Works like an Else. With console.log, you still need to do if/else.

return num % 2 == 0 ? 'even': 'odd'  this makes a single line if / else statement. the : is a TERNARY and acts as an if / else.
              conditional^     ^do this if false
Javascript Data Types:
<!-- Strings -->
Denoted with "" (double quotes), ''(single quotes), and ``(backticks)
Must always end with ; to end the syntax.

<!-- Numbers -->
Any whole number is an integer.
.x works too, but don't ever start decimals with a 0.x.
Decimals are considered numbers. 
Number (must be capped)

<!-- Boolean -->
True or False. No more no less

<!-- The weird ones -->
null
undefined
NaN

<!-- Objects -->
{};
Object

<!-- Arrays -->
[];
Array

Be specific with your variables. let hero not specific enough. heroHealth, heroName

<!-- This only happens when the function is called upon -->
function helps save something for later. the block goes into the function.
function shouldMilesDrinkThisPotion(){
  if(hasHealthPotion){
    heroHealth += 50
  }
}


Usually better to deal with your out conditions (fail conditions) first.
if(!x) == ! means "not". if (!hasHealthPotion) = there is no health potion.

Math.floor = round down
Math.ceil = round up



<!-- SECTION TUESDAY MAY 2 -->
LOOPS // ARRAYS // DYNAMICALLY UPDATING DOM

<!-- NOTE            V PARAMETER -->
function accuseAnimal(placeholder){
  console.log(placeholder)
}

to make sure the function is active
functions can be defined to take in parameters. In a function definition, you can specify a name. 
function this(x) x=argument.
Placeholder best practice: describe it as it is. 

parameter = definition when defining the function
argument = the actual data sent in. 
"null" can be anything you need it to be.

* handle - go do this. Hands job off to another function. 
* options - picks from the list of items in the array
* keys = options
* switch = switches between id's
* case = denotes the id


switch(clueKey){
  case 'weapon:
  if(xx){
    }
  case 'home':{
    
  }
}

target an index of a string the same way as an array: return str[position]
join 2 strings: 
return `${str1}${sepeaator}${str2}
return str1 + separator + str2 

returns a string, capitalizes the character at target position, works with any length of string
return str[position].toUpperCase()

"reference error" most likely means you need a string

<!-- SECTION Wednesday, May 3rd -->
Pseudo coding: writing out what you want to do in longhand: find the sandwich, add the price, etc.
functions = bruce lee: fear the function that does one thing super well, not the function that does a hundred things okay.

very first line in a function should always be console.log() that way you can test it easily.
onclick should always be in a button for accessibility requirements.


<!-- SECTION Thursday, May 4th -->
* | is shift + \ (Pipes or Sticks (sticks is cooler))
* || = "or" in functions
* "offset" is essentially a col-6. Fills the empty space instead of putting in an extra empty column.
* add a cursor in css to better show the object is clickable
    in style.css: user-select: none;
* user-select removes the highlight when you click the object.
<!-- Intervals -->
setInterval() 
Intervals work in MS. 
don't invoke "()" intervals.
InnerHTML is used when you want to adjust things and there are more elements than text being used. Also uses the `` to make work (inter-something). The tilde, under the 'esc' button.
InnerText is used when it's only text being changed. 

animals.forEach(animal => {
  switch(animal.mood) {
    case "x":
    break;
    case "y":
    break;
    default:   (default is what is done if x or y etc. aren't met.)
  }
})
 
 is equivalent to
 animals.forEach(animal => {
  if(animal.mood == "x") {
  } if else {
    animal.mood == "y"
  }
 })

marquee behavior ="alternate" direction="up, left, etc." scrollamount=
marquee: HTML class to add animation of scrolling.
marquee can have multiple lines of behavior and directions.
Wrap the elements you want to move in the marquee tags. 
marquee.stop causes the marquee to stop moving.





<!-- SECTION for tutor request -->
Parameters / Arguments are still a little confusing.
Invoking strings
Ternaries. Still confused about those too for the most part. I get that you're essentially asking a question then answering it, but that's as far as i know

<!-- SECTION tutor -->
FUNCTIONS & ARRAYS
Draw = need an id="" to draw from the array.
function draw^name of array^ usually is best. 
function drawAnimals()
template - stores all HTML that we want to apply for that function. usually only seen in draw functions.
animals.forEach(a => template += ` insert the html for string interpolation here`)

argument goes into the DRAW function.
Parameters go into the function name.

<!-- SECTION FIRESIDE -->
