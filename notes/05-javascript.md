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

