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

<!-- SECTION Tuesday,  May 16 -->
* sandbox.codeworksacademy.com - it's an API for us to mess around with.
* the keys under the header are the same keys we'll be using in the lab.
* env = environment. this is what loads the environment for the application.
* .handleRouteChange() listens for the #changes and acts accordingly with changing the path.
* api = application programmable interface
<!-- 1. bcw create -->
<!-- 2. mvc auth. name your project. n on init. open. -->
<!-- 3. start with bcw live. -->
<!-- 4. grab the keys from the site and paste them into the env. take them and post them accordingly to the clientId, audience, & domain. -->
<!-- 5. swap the baseURL to the sandbox.codeworksacademy.com. then save. -->
<!-- 6. click login. -->
<!-- 7. add <a> in the index for an href with the link you want to setup. -->
<!-- 8. build new controller for the href you want sent -->
<!-- 9. export then constructor then console.log to make sure it's connected. -->
<!-- 10. go to router to add the path.  -->
11. build a service for the tab you're wanting. class xService. out of the {} make your export constxservce = new XService.
12. make sure to put async before the function the await is going into. in the async 
13. write an async function in the controller that's named the same as the service. try catch pop error to make sure the function works. don't forget the await within the async.
14. model > new file > xxxxx.js > export class xxx > constructor(data) this.x = data.x
15. get xCard(){ > return /*html*/ then basic layout of the card we want. } > layout for this card is on the car model for today's lesson.
16. pass into the appstate. still on the model portion for reference.
17. add the @type import wherever this was supposed to go.
<!-- you can make sure the html from the other pages doesn't show up on the page you want to by refreshing. horrible way to set up though. -->
18. for loading to the page, function _drawX on the controller. let template = '' > appState.cars.4each c template > set HTML('x', template)
19. in the constructor, for the export class, add the AppState.on('x',_drawX). 
<!-- STUB adding functionality to only show create things if you're logged in -->
20. in the model, return /*html*/ then static xForm {add form here} !!!!!!don't worry about adding the creator. that's done on back end!!!!
21. head to index. grab bootstrap modal and put it in under the main. give the modal the id.
22. update the modal each time the page loads. in in the export controller, setHTML('modal name;, X.XForm). double check all imports are set.
<!-- STUB modal info -->
23. data-bs-toggle="name" data-bs-target="#name" to open the modal on the page. link it in the <button>. Toggle tells BS what it's going to toggle. Talks about what kind of BS data it'll be messing with. Target tells it what it'll target. The ID or name of what it'll be calling to. toggle and target aren't always the same. 
<!-- end modal info -->
24. make the button for the modal not show up unless they're logged in.make a <div> in html but make the class a custom one to reference where it'll go. go to the xController then in the constructor, setHTML('name we chose for the button').
25. go to the other controllers and copy over the set html to the constructor, but remove the information about the modal but leave the id. that way it'll grab the element, but it'll be empty so no butotn for it to grab unless you're on the page you want to be on. 
26. appState.on('account', _drawButton) in the controller to listen for when we're logged in.
27. funciton _drawButton(), if (appState.account) {then copy over the setHTML with the modal in it.} 
28. in controller, async createX() try/catch > pop.error(error). > window.event.preventDefault() in the try portion of the function.
29. const form = widnow.event.target under the preventDefault. > const formData = getFormData() this passes in the form. console.log to make sure it works.
30. await xService.createX(formData) > form.reset()
31. async createX(){ const res = await api.post('api/x;, formData)} this pushes the information to the api and posts the information to the page. > console.log('xxxxxx', res.data)
<!-- STUB DO THIS IN THE CONTROLLER LAYER -->
31.5 boostrap.Modal.getOrCreateInstance('# whatever your modal's id is').hide() 
<!-- END STUB -->
32. in the service of the async createX, add const newX = new X(res.data) > AppState.x.push(newX) > AppState.emit('x')
<!-- STUB DELETE BUTTON AND REQUEST -->
33. go to the xCard, make your delete button on the card wherever fits best. add onclick="app.xController.deleteX('${this.id}')"
34. go to xController, under the create add async deleteX(id), add the try/catch/pop.error. add const yes = await pop.confirm(), if (!yes){return}
35. xService = deleteCar. 
36. in service, async deleteX(id), const res = await api.delete('api/x/'+id)
37. appstate.cars = appstate.cars filter 
38. in the model, do get deleteButtonIfCarIsYours(){ if (this.creatorId == appstate.account.id) {return delete button from earlier) }return``}. example on bottom of car.js from today's example.
39. go to controller, in the xController, appstate.on('account', drawX)
<!-- ? is the elvis operator. allows us to safely access the account if it's null. if tehre's nothing there, it stops. if there's something then it'll investigate.  -->



<!-- SECTION WEDNESDAY, MAY 17 -->
* Puts are the focus today - essentially an update
* Spellbook example will be super useful this weekend
* building the controller first allows you to start testing things off the bat
* nice design thing to have listeners on top
* reference the network tab in the inspect to see the URL and see if we missed something. 
* inputs get an onchange. onclicks register on the click, but inputs can wig out when they get clicked. we want to tie into the change state of it, not the click.

<!-- 1. in axios, click on api, F2, change 'API' to sandboxApi. -->
2. copied down the sandboxApi and changed to dndApi. Also added the interceptors.request for the dndApi.
3. build first controller - spellsController. Starting with the most familiar. export class SpellsController
4. constructor then console.log
<!-- 5. got rid of the extra things in the router. replaced the only path with the SpellsController since that's the main thing we need anyway. -->
<!-- 6. class SpellsService { export const spells  new spells } -->
<!-- 7. async getSpells() const res = await dndApi.get('/api/x') > console.log (res.data.results) .results is where the data is actually located. go deeper. -->
8. async getSpellsFromDndApi(){ try, catch, pop. error. await SpellsService.getSpells()} 
9. in appState.js - spellDex = []
10. spellsservice appstate.spellDex = res.data.results
11. scontroller setup listener. appstate.on('spelldex', draw spelldex)
12. scontroller function _draw sdex() {console..log('sdex', res.data.results)}
13. scontroller let template = '', appstate.sdex.forEach (s => template += /*html*/` make the template in the string interpolation`)
14. added to the interpolation
15. async setActiveSpell area
16. build it out in the HTML for it to draw to the page. the spelldex id area on the lecture from today.
16. setHTML('spellDex', template) in scontroller.
17. build model. activespell.js
18. export class / constructor then build out the model. to convert from array, data.desc?.join('<br/>') in this example since the spells come in as an array but we need it as a string.
<!-- <br/> is a line break.  -->
19. after building the constructor, add the get ActiveSpellCard return /*html*/ and build the html under it.
20. in spellsservice  appstate.activespell = new acivespell(res.dat)
21. in appstate, activeSpell = null and chagne the import
22. add activespell to the listener
23. in the controller, function _drawActiveSpell(){ setHTML ('activeSpell, appstate.activespell?.activespellcardtemplate)}
24. add the button to make sure it doesn't work unless someone's logged in. make the button in the model. in the button, if appstate.account return /*html*/ login button } return /*html*/`insert butotn here`
25. call ${this.spellbookbutton}
26. new controller. userspellscontroller. export class blah blah blah. constructor console.log to make sure it's hoooked up. async addspell try catch pop
27. add this to the app.js
28. create userspellsservice - class userpsellsservice / export const
29. userspellscontroller - await userspellservice.addspell()
30. userspellsservice addspell() const res = sandboxApi.post('api/spells', appstate.activespell) then console.log
31. userspllscontroller async getuserspells - try catch pop - await userspellservice.getuserspells - const res = await sandbox.get('api/spells'). console.log('', res.data)322 
32. in the userspellsonctroller - constructor - appstate.on ('account' this.getuserspells)
33. userspellsservice - getuserspells - appstate.userspells = res.data.map(s. => new Spell(s))
34. appstate - userspells = {} and change the import
35. userspellscontroller - _drawuserspells in the appstate.on under the constructor. function _drawuserspells - console.log('drawing spells',appstate.userspells)
36. in the spell model, get UserSpellTemplate, return /*html*/ then build out the template. example is on line 44 in the spell model from today. 
37. userspellscontroller in the drawuserspells, console.log('', appstate.userspells), let template = '', appstate.userspells.forEach(s => template += s.userspelltemplate) sethtml
38. go back tot the userspelltemplate and add a checkbox. add 'checked' to the template.
39. get preparedCheckbox() to see one way. add onchange ="app.userspellscontroller.togglepprepared('${this.id})"
40. userspellscontroller - async toggleprepared(id) - try catch pop - await usersspellsservice.togglespell(id)
41. userspellsservice - const spell = appstate.userspells.find(s => s.id == id)
42. userspellsservice - toggle spell spell.prepared = !spell.prepared  // cosnt res = await sandboxApi.put('api/spells/' + id, spell) // console.log('', res.data)
 


<!-- SECTION THURSDAY, MAY 18 -->
* apod - a picture of the day
* x-rate-limit is the amount of requests we can pull from the api in a day.
* x-rate-limit-remaining is how many more we can take.
* without the api key, we have no access to the api. gives an error 403.

1. went to the env.js to add the domain and such.
2. added new controller. nasacontroller. export class X( constructor() {}) console.log to test.
3. added the controller to the router. made the home contoller an array. [hommeController, xController]
4. in the axios service, put in the get request for the new api site. added params{api_key: ''} This allows us to view the api from the site.
5. nasacontroller async getpictureofday() try catch pop to check for errors. await nasaService.getpictureofday()
6. created nasaservice. class nasaservice{} export const nasaservice = new ns.
7. nasaservice async getpictureofday const res = await nasaapi.get(). console.log
8. created new model. nasapicture. export class nasapicture {constructor(data)}. this.x = data. x
9. console.log again in the nasaservice. ('x', new Nasapicture(res.data))
<!-- this way it auto imports into the model for a new one and pulls the data from it instead of mapping. gets the information, compares it to the model, then brings it back to us.
you can put debuggers in the model to make sure it's working if you want to. -->
10. in the appstate, nasapicture = null. copy down the import and adjust it. 
11. nasaservice - getpicutre funciton- appstat.enasapicture = new nasapicture(res.data)
12. in the nasacontroller - funcitondrawpicture(){ document.body.style.backgroundImage = `url(${this.picture})`} also added const picture = appstate.nasapicutre above it.
<!-- this manipulates the style of the body without needing to go into CSS.  -->
13. invoked  _drawpicture() down in the consturctor with appstate.on('nasaPicture',_drawPicutre) above it. 
14. in the css, changed body to what it says for the body in today's lesson.
15. go to the index.html to build out the layout of the page.
16. give the row you want this template in an id to use.
17. copy the template over to the nasa model. get nasapicutretemplate() return /*html*/. paste the template into the model. 
18. in the nasacontroller, under _drawpicture, setHTML('pictureinformation", picutre.nasatemplate)
19. add in input: date into the html - add in an onchange with selectDate()
20. in the nasacontroller, async selecDate() { try catch pop await nasaservice.picture}
20. test it
21. in nasaservice async selectDatre() { const res = await nasaapi.get('?date=')}
22. in nasacontroller selectdate let dateElem = docu.getelembyi('id) // let datevalue = dateelem.value
23. add date to sleectdate in the nasa service and string interpolate below it.\
24. in nasaservice async seletdate, add appstate.nasapicture = new nasapicture.
25. added sandboxcontroller - export class sandboxcontroller - constructor - console.log
26. added sandboxservice - calss sandboxservice - export const sboxxservice = new sandboxservice
27. added [..., sandboxcontroller ] to the router 
28. sandboxcontroller - async favoritePicture try catch pop await sandboxservice.favpicture()
29. sandboxservice - async favotirepicture(favoritedata){ cosnt res = await api.post(favorite data)} - console.log
30. sandboxcontroller - let  in favorite picture favoritedata = appstate.nasapicture
31. ad the favorite to html for adding to your favorites. onclick=app.sandboxcontroller.favoritepicture()
<!-- 32. sandbox controller maybe. async quick await sandbox service.quick -->
<!-- 33. sandboxservice async quick asdfljklasdfhlkajsf -->
34. appstate sandboxpicture = null
35. new model sandboxpicture - export class sandboxpicture - constructor (){ input the data that comes from the sandbox api. }
36. sandboxservice appstate.favoritepicture.push(new sandboxpictures(res.data)) - appstate.emit("sandboxPicutres")
37. sandboxpictures = [] instead of null
38. in sandboxcontrollers - async getfavoritepictures (){ try catch pop await sandboxservice.getfaovritepictures()}
39. sandboxservice - get favoitepictures() - const res = await api.get('api/apods') - console.log ('', res.data.map(p => newsandboxpicture(p)))
40. sandboxcontroller - export class sandboxcontroller a-appstate.on('account', this.getfavoritepictures()) - this.favoritepictures
41. sandboxservice - appstate.sandboxpicures = res.dat.map (p => new sandboxpictures(p))
42. add everything for the offcanvas
43. sandboxcontroller - function drawfavorites() - let template = "" - appstate.sandboxpictures.foreach(p => template += p.favoritetemplate) - setHTML('favoritepicuttes', template)
44. sandboxcontroller - sbc appstate.on('', getfavoritepictures)
45. sandboxpicture - get favoritetemplate() { return ``}
46. in favorite template, add onclick"app.sandboxcontroller.removefavorite()
47. async removefavorite () { try catch pop.error awaitsandboxservice removefavorite()}
48. sandboxservice - async removefavorite(favoriteid) const res = await api.delete(`api/apods/${favoriteId}', )
49. sandboxservice - removefavorite - appstate.sandboxpictures = appstate.sandboxpictures.filter(p => p.id != favoriteId)
<!-- put requests to flip the boolean -->



<!-- SECTION Thursday, May 25 -->
<!-- STUB HACKATHON PREP -->
* localField: on the schema. ForeignField: what's on mongoose. the "toJson" is needed to be able to use the virtual

1. on github, new repository, name it. 
2. init commit. add collaborators > settings > collaborators and teams > add people 
3. create bird model. export const BirdSchema = new Schema. import mongoose & schema
4. name type: string required, imaage type string required, canFly type boolean, size enum type string, timestamps true toJson virtuals true since they're many:many, birdWatcherId type schema.type.ObejctId required, reference account ( that way we know who made it.)
5. for the virtual: BirdSchema.virtual('birdWatcher'){ localfield: 'birtdwatcherid', foreignfield: '_id', justOne: true (booelan doesn't go in string),}
6. register schema in dbContext
7. build the controller. export class birdscontroller extends basecontroller{constructor super('/api/birds/'), this.router}
8. build the service. class birdservice. export const birdsservice = new birdsservice.
9. back in the controller, .get('', this.getBirds), then make the get birds. async getbirds(rrn) try catch next, const birds = await birdsservice.getbirds(query). const query = req.query. return res.send(birds). 
10. in the birdsservice, async getbirds(query), const birds = await dbcontext.birds.find(query), return birds
11. new collection in postman. new get request get birds. add the baseurl variable to the main folder. in the get, baseurl/api/birds. save.
12. back in the controller. .post('', this.createBird). async createbird(rrn) try catch next return res.send(newbird). const birddata = req.body. const newbirds = await birdssservice.createbird(birddata)
13. in the service, async createbird(birddata), const newbird = await dbcontxt.birds.create(birddata) return newBird. spin. 
14. in postman, new post request. basurl/api/birds. raw. json. make the object {}. copy over information from the model. 
15. spin up the client. grab the bearer token from localhost: 8080. inspect. network. fetch. click on the token. copy access token. on postman, under the main folder. auth. paste it in both values. authorization. bearer token paste.
16. in teh controller. .use(Auth0Provider.getAuthorizeduserInfo). req.body.birdwatcherid = req.userinfo.id. 
17. in the service. in the createbird, await newbird.populate('birdwatcher', 'name picture'). save. spin.
18. in postman. create bird. send. build the birds in postman
<!-- 19. back in controler. .get('/:birdId', this.getbirdbyid), getbirdbyid(rrn), try catch next return const bird = req.params.birdId, const bird = await birdsService.getbirdbyid(birdid), return res.send(bird) -->
20. in the service, async getbirdbyid(birdid), const bird = await dbcontext.birds.findbyid(birdid), if(!bird) {throw new badrequest('no flyinzone'), .populate('birdwatecher', 'name picture'), return bird. save. spin. 
21. new request in postman. get birdbyid. copy over an id from the array we made. paste id. make sure it populates and works. 
<!-- STUB FRONT END -->
22. copy the url down, git clone, paste, open, huzzah. 
23. add .env to the server level. paste in the information from the previous version. opeen the terminal. type nmp i to get the .envy, mongoose, all the other folders that are needed to spin the server and make everything work as it should. 
24. bcw serve. open. inspect. make sure there are three network requests. 
25. start building the homepage. sketch the bird card out. 
26. create the birdscontroller & services and setup imports. 
27. in the service, class bridsservice, export const birdsservice = new birdsservice()
28. in the controller, export class bridscontroller, constructor, console.log, register the controller in the router 
29. check the page to make sure everything works. 
30. in the controller, async getbirds(), try catch pop birdsservice.getbirds(), put this.getbirds in the constructor. 
31. in teh service, add getbirds(), const res = await api.get('api/birds'), console.log('[getting birds]', res.data)
32. make bird model. xport class bird{}, constructor(data), go to the network, copy object, this.id, this.name, this.img, this.canfly, this.size, this.birdwatcherid, this.createdat, this.watchername, this.birdwatcher, 
33. into the appstate, new collection. birds = [], import change to birds.
34. back in service, appstate.birds = res.data.map(b => newBird(b)), console.log(appstate.birds);
35. copy the bird card template from the index, comment out, paste in the model. get cardtemplate{``}, 
36. to the controller, function _drawbirds(), let birds = appstate.birds, let template = '', birds.foreach(b => template =+  b.cardtemplate), setHTML('')
37. back to the index. messed with divs and container fluid on the hteml. around line 73. cut
38. home views, export const homeview = /*html*/ added the cut portion to the page to show what the main page will look like. 
39. in the controller, place appstate.on('birds", _drawbirds) in the controller. 
40. adding an onclick to the modal in the model. set activ, pass in the id,
41. in the controlle,r async setactive(bridid)j, try catch error, birdsservice.setactive(birdid,), console.log
42. in the service, set active(birdid), const bird = appstate.birds.find(b=b.id==birdid), console.log('[settingactive];bird)
43. in the appstate, activebird = null, import and fix to above on line 19. 
44. in the service, add appstate.bird = activebird (i think)
45. found a modal. pasted it in the homeview. gave it an id to reference it. added data-bs-toggle="modal" & data-bs-target ='#modal' to the card template
46. in the homeview, changed the title and added a container to the body. sections row, div, img, h1, mess around with that. 
47. in the controller, do function _drawactive(), let bird = appstate.activebird, setHTML('modal-guts', bird.birddetails)
48. after making the static bird form, added getbirdofmr in the controller. sethtml(')
49. create brid in the service.
50. in the ascync service createbird appstate.birds.unshif(new bird(res.data)) unshift doesn't emit.
<!-- STUB BACK TO BACK END FOR VIEW COUNTS-->
51. create new model: spotter.js for spotting the bird. 
52. export const spotter schema such and such, bidid: {type, chema.types.objectid, required: ture, ref: 'bird'}, watcherid {type: schema.types.objectid, required true, ref 'account'}, timestampes true, tojson:{virtuals true}
53. spotterschema.virtual('spotter'), localfield: 'watcherid' foreignfield:'_id', justonce: ture, ref:'account', THIS IS A VIRUTAL FOR THE WATCHER
54. build spotter controller & service. in controller, export class spotterscontroller extends basecontroller, constructor, super('api/spotter'), this.router, 
55. in spotter service, class spotterservice, export const spottersservice = new spottersservice. 
56. back in the controller, .post('', this.becomespotter), .use(auth0provider.getauthorizeduserinfo)
57. async  becomespottter(rrn), try return catch next, req.body.watcherid = req.userinfo.id, const spotter = await spotterservice.becomespotter(req.body), return res.send(spotter)
58. in the service, async becomespotter(body), const spotter = await dbcontext.spotters.create(body), await spotter.populate('watcher', 'name picture') return spotter,  (DON'T FORGET TO ADD TO THE DBCONTED)
59. back to postman. add post request. baseurl/api/spotters, body, raw, json, just have birdid & watcher id. populate them 
60. in the controller, .get('/:birdid/spotters', this.getspottersbybirdid), then the function down below. async getspottersbybirdid(rrn), try catch next return, const spotter = await spottersservice.getspotterbybirdid(birdid), const brid = req.params.birdid, return res.send(spotter)
61. in the spottersservice, async getspotersbybirdid(birdid), const spotters = await dbcontext.spotters.find({birdid}), .populate('watcher', 'name picture') return spotters
62. in postman, add get request getspotters by bird id, add the baseurl,
63. in the bird model, birdschema.virtual('watchercount', localfield: '_id', foreignfield: 'birdid', ref: 'spotter', count: true) 
64. in the service layer, in the getbirds, .populate('watchercount') and also populate it in getbirdbyid, and also in createbird, add .sort('watchercount') to getbirds, 
65. in the spotter model, spotterschema.index({watcherid: 1, birdid:1,}, {unique: true})
<!-- STUB BACK TO FRONT SIDE -->
66. added stuff in the spotters controller & service