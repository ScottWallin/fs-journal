# HTML

Week 1, Day 2 (April 25, 2023)
Always start with the basic skeleton: ! then "enter"
<head> always reserved for information given to the browser.
<body> contains everything the user will see on the page.
<header> contains stuff in the header of the page and the <nav><nav>
<section> = blocks in the page and goes in <main> 
Blocks are broken into two sections.
<div class="right"><div>
<div class="left"><div>
under the final <main> goes the <footer><footer>
head
body
header
main
footer
link - tab then style.css under href, then cmd click and it'll create a style.css to use
:root{} in CSS is where you place all your references to use for other elements in CSS.
Setting an element to "flex" affects all of that element's children and makes them align horizontally by default. "flex-direction: column/row;" sets their alignment.
In the body, set the min-height to be 100vh (vh = view height). 
Set main to flex-grow: 1; and that sets main to fill all the available space. 
div*x generates x number of divs
Parent element gets the flex. class= "d-flex" = display flex
shift + arrow key selects as the cursor moves to the right or left.
cmd + shift + arrow jumps to the beginning or end of the word.
.(class) is a utility class. Usually only has a couple things in it. 
.d-flex{ display: flex; flex-wrap: wrap; } is a good general style to have for displays as you build your site. 

css - align-items-baseline{align-items: baseline}
baseline is just one of the options. the rest can be found in the terminal on the site under the elements in the dev tools. 
margin box model pushes out. border changes the edge. padding pushes the content inward.
rem > px for sizing.
.justify-content-between{justify-content: space between;} balances the spacing between the items evenly.
gap - customizable space between elements. 
<article> groups <p>
