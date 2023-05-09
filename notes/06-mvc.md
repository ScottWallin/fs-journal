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
