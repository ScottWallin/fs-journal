# MVC

<!-- SECTION Monday, May 8 -->
* bcw create: starts a project template from the terminal
* constructor(data) is responsible for building things
* singleton pattern - design pattern - there is only one heroesService
Design pattern - underlying principle of code design to make sure the code doesn't break. 
Application design pattern - designed to scale for an entire application.
MVC applicaiton design pattern is one of the main standard ones. Most are built on this pattern.
Model / View / Controller = MVC

if you're in a class, and write "function" in front of a function, it breaks things. you'll write your function in classes without writing "function' in front of it. that's code thing, not an MVC thing.
observer pattern - not technically part of mvc. underlying design pattern that usually is slotted into mvc to help strengthen it.

Constructor is key word (special function used for building AKA instantiating a class) for an instance of a class. We can ask the constructor to build us something or give us a model. Constructor takes in (data) or raw material. 

@param {{name: string, health: number, level: number}} data

constructor(data) {
  this.id = data.id || generateID()
  this.name = data.name
  this.health = data.health
  this.level = data.level
}

The controller's job is NEVER to modify data. It can, but it shouldn't. 
Difference between HTML ID's and data ID's. html: tag to reference for change to be made. Data: reference to a data sheet. 

<!-- SECTION Tuesday, May 9 -->
With MCV, the model section is where you usually want to start. Gives you the bones to build on.
<!-- STUB -->
it's a good practice to start with export as the first thing. If we want to reference this class elsewhere in our project, make sure to add an 'export' before defining it.
<!-- end stub -->
 Helps to think of the class in the model as a CSS class. Only spiky brackets, no others. Define the class the same way you'd define elements in CSS.

 constructor() is what invokes the blueprint. 
 export class House{

  
  constructor(walls, floors, windows) {
    this.walls = walls
    this.floors = floors
    this.windows = windows
    this.crownMoulding = true
    this.lightbulbs = 0
  }
 }

 new House ({walls:'plywood', floors: 'tile', windows: 'glass})

 When invoking a new House class, it'll pull the walls, floors, and tiles, for each new one. 
 The class/model is what i want m data to look like, the AppState is where the data is stored. It's stored in the spiky brackets within the -
  'class AppState extends EventEmitter'{

 house = [
  new House ({name:'x', floors:'x', windows:'x'})
 ]}

 name your Services as what will handle that specific model. HouseService.js.
 Service layer is where you start adding or manipulating information. Services are for the 'business logic'. Anytime I want to manipulate or alter my data 

 * (AppState), it will happen in the service layer. 
 class HouseService {

 }

 export const houseService = new HouseService. It's only this single instance of the service that's used, not the base service because that holds all the important and private information. 

 Controllers are like the 'filter' layer between the users and the rest of the code. Anything that  a user can interact with will come through the controller first.
 App.js is the portal between HTML and the rest of your code.

 class App{
  houseControler = new HouseController()
 }
 check the template under gachamon.js for sam's project today for the example of the template to use.
 
 get x adds another property to an object for the array. For an additional function or method or bringing into HTML. ADDITIONAL PROPERTY FOR A CLASS

 export class HouseController {
  <!-- if i want something to happen as soon as the page loads, as soon as this controller 'mounts, put it in the constructor -->
  constructor () {}
 }

 * cmd + . declares the method to the next layer.
 Services can be called inside of other services.

<!-- SECTION FIRESIDE W/ JORDAN -->
For imports, make sure import you're linking, does have a link attached to the intelisense.


<!-- SECTION Wednesday May 10 -->
Modals data-bs-toggle: what kind of component do i open?
data-bs-target: open this modal.
They work as an onClick()
Modal-content: the content of the modal. Inside of this is what's actually displayed in the modal.
Modal-header is the title of the modal. The title you want it to show.
Modal-body is similar to the body of the html. can have divs rows and columns.
in the modal-dialog is where you'd also add the size of the modal.
for= and id= on forms should match
preventDefault keeps the page from refreshing.
static vs get - static doesn't get/set every time you instantiate. it's just static to the class. Static exists on the class so when you call it you don't need to do app.x.x 
Get is a pproperty that's created every time you click new 'x'
name= tags it into the value to 

how to know when to use get vs static.
get use: unique template for each one i use. String interpolation is a good notifier of when to use get. if the info doesn't need to change. the form doesn't need to change, but the information does. the unique instance or property changes with each use. 
static use: if the information doesn't have to change. 

local storage: saveState('id', appState.x)
if (input) return = requires there to be an input for the thing to log. without that input, it won't work.

car.js line 116 is what is used to make it so the button is disabled if there is no user name given. also carscontroller line 35 &

car line 110 for delete button

<!-- index, model, dummy data in AppState, build the controller, register controller in the App, build service page, after pages are set up, console.log like crazy, draw, win. -->

<!-- SECTION MAY 11 NOTES -->
KEEP TRACK OF ORDER OF STEPS IN NOTES.
* 1 bcw create then index. build your layers specific to each element you'll need.
* 2 Starts with creating the model

export class x, constructor(data), this.id = data.id || generatedId() good place to start. then go with your this.x for whatever descriptors you'll need for the project. 

* 3 dummy data in AppState. under class appstate extends eventemitter {xxxxxx} content goes between spikies. 
* 4 build your controller. register the controller in App.js (xController = new XController())
* 5 build your services.

class xServices{}
export const x Service = new xService()

* 6 index.html. space things out. comment out the stuff in main. main/container-fluid. row. col's to build out the layout. Section things out. build out your template with the <p> and <h> tags. comment it out and copy it to make the template. 
* 7 get xTemplate() {
  return ` *tilde next to 1* paste in template copied over. replace things between p and h tags with ${this.x}
}
* 8 jump into controller to draw. function _drawX(){} console.log to make sure it's drawing to the page. repeat _draw in the constructor(). let x = appState.x / let template = ''
x.forEach(x => template += x.template). setHTML('x', template). || don't forget to put the id in the html file where you want the template to go.||.

* in the model tag - for newDate() - get ComputeDate(){ let date = this.date | return (date.getMonth())+'/' + (date.getDate() + '/' + (date.getFullYear))}
* to limit what's seen in a preview: get ComputeTitle() {return (this.x.slice(0,15) + '...')} in the slice it specifies what is seen. based off character. not word.
* to make active, add the "onclick" in th div in the template. onclick='app.xController.setActive()' don't forget the app.xController!!
add the setActive(){console.log()} in the controller under the constructor. in the parenthesis of the setActive add setActive(')
x.Service.setActive(xId).
* copy import in AppState. then activeX = null. in the Import do x|null as well.

* hard code the template in HTML for the activeX. example is on line 44 in the index.html of today's lesson. with text areas, width must be specified in the class. copy template over to the model.
* make activeXTemplate(){ fill in template where things are needed to be changed.}

* function _drawActiveX(){ let activeX = appState.activeX | setHTML('', activeX.ActiveXTemplate)}
* under the constructor add the appState.on_drawActiveX.
* in the AppState, classifiedWords =[] does an array of redacted words that you don't want shown. changed in the model.
* add get ComputeRedactedX(){let originalXArray = this.x.split(' ')}
<!-- information for above on line 53 in the case.js for today's lecture. -->
<!-- split looks for the spaces and removes them to push the word out. -->
* let redactedXArray = originalXArray.map(word => {
  <!-- for capitalized -->
if(appState.classifiedWords.includes(word.toLowerCase())){
  return ' black squares ' } else{ return word }
  return redactedXArray.join(' ') 
  <!-- join returns the array together. -->
}})
* .map covers the matching logic with what was specified. map transforms array to new array.
* to remove redacted. copy the template because we'll be switching between two templates. redacted template / unredacted template.
* for the redacted one: get redactedXBody. for the unredacted: get .xBody.

* Always make sure to register your new controllers in the app.js 

* Name and property must align for the input to take.

<!-- STUB UX / UI THINGS -->
* document.querySelector(.'reportBody').focus() ----- automatically drops the cursor into the report body
* in the model, onblur (in the textarea) automatically saves the text if i click outside of the text area.

<!-- SECTION Monday, May 15 -->
* try catch to see about an error. put the function in the error. put Pop.error and it'll tell you what's wrong.
* promise isn't data. promise is the await.
* .map(x => '') takes the individual item and converts it to a new array. processes each item in the array to a new one.
* when working with styling, comment out the getter. some api's limit how many times you can get the information in a time limit and refreshing pulls that count down. 

1. bcw create - mvc
2. get rid of template stuff with the valuesController
3. created character.js in the model
4. export class Character - constructor(data) { this.id, name, alive, image, wizard}
5. get CardTemplate() return /*html*/` <div>${this.name}</div>` to make sure it works
6. made CharactersController.js to export the charactersController. constructor(){console.log()}
7. register charactersController in the app.js
8. in the appState made characters =[] then appState.on('character', _drawCharacters)
9. above the export class function _drawCharacter(){}
10. added charactersService.js - class charactersService {} export const chacatersservice = portion of the service
11. go to characters controller and import the service
12. on the controller, added goGetMyCharacters .... (){ charactersService.goGet ....}
13. made that funciton async. means: will do the thing but not sure how long it'll take. needs an event listener. add "await" before the function inside the async. go into the service and add async to the service function as well.
<!-- STUB this was the setup and now for the API -->
14. in the index. add script - axios in the body  but under the header. Axios gives access to the library axios. gives back a promise. in the inspect, go to network and check Fetch. shows everything that can be obtained. 
15. axiosService. added the baseurl which was up to .com/
16. linked the hpApi.get('/api/characters')(this was the rest of the url) under the async. adding the last bit of the url here allows us to go into the base url then go into the next part to retrieve whatever specific item we wanted to get. 
17. const response = wait for the result of the thing. this was put before the async
18. res.data gives the array of the amount of data.
19. appState.charcters = response.data.map(c => new.character()) gave the information from the draw. but all it gave was pojos. simple information.
20. did the for each on the characters controller under the _drawCharacters()
