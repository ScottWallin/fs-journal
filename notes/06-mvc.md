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