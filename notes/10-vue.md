# Vue
<!-- SECTION Tuesday, May 30 -->
* vite config - 
* pages = controller in vue. 
* template has the html, script has methods/functions, and the styling all are in the page. 
* very component based framework. components serve as chunks of reusable code. 
* page components are mounted in the router now instead of controllers 
* app.vue is the main window to the application. It's the front door. 
* router view is where all of the routers draw. placing that in the page fills the content of the page with what's inside that page folder
* writing things in the app.vue file, it'll stay hardcoded throughout the DOM regardless of the page you're on. 
* computed - listens to the appstate. this pulls in and uses the reactive data. 
* v-if is an if statement in vue. v-if ="account.id" waits for if the account has an id. in the exoprt defualt, having account:computed (()=> Appstate.account) lets the appstate search for an account on page load. 
* in the return section o fthe hoempage under export, each of the functions you add allow what's on the left of the colon to be what the tag that searches for the information. 
* methods first then computeds. methods don't need "function" in front of it. incrementNumher(){ this.number++} is the function in today's example. 
* v-for is the for loop
* for bringing in the component, just <Component /> is all that's needed to bring it in
* in vue, vt brings up the template/script/style in the component. 
* when putting content into a self closing tag, make it into a conventional tag. 
* v-model="editable.x" allows the informaiton to be edited. the .x opens the path for the edit. if you want to edit a body, put editable.body. if you put editable.body in the title, it'll still edit the body so make sure the .x is in the right spot. 
* for UI, if you're going to use an icon on a butotn or as a button, you must have a title tag that denotes its purpose.


1. bcw create - vue starter - name
2. built a new path in the router.js for cars. starting line 21.
3. over to the pages, build a cars page. 
4. made a view template. make an h1 or p to make sure it's working and loading to the page. 
5. in the navbar, use the about one as a reference for how the car tag is made. router-link talks to the router page to build the path in the router. :to gives the path direction. 
6. in the script, added the async await try catch pop for the getcars. added the onmounted, note above talking about what it does. works similar to a constructor in a controller.
7. added async getcars in the service. const rest.
8. add the empty array of cars to the appstate.
9. made a car model . export class. add data
10. added appstte.cars in the service. 
11. in the carspage, added cars: under on mounted.
12. treat pages like containers. build the template for the page layout in the cars page
13. added a details path to extend the path for each car clicked on
14. details page made.
15. adding the create button then creating a modal vue with the template, script, and style. then import the modal into the app.vue and give it an id to target and reuse. 
16. added the return types into the export of the car form
17. const editable in the carform.

<!-- STUB Fireside with Sav -->
1. useRouter() has different paths. Sends to other locations. useRoute() is about getting different pieces of information

<!-- SECTION Wednesday, May 31 -->
* it's good to get the api before building the model. that way you can see what their api contains to pull into the model. 

1. Line 9, in the axios, added export const movieApi to import the api we'll be using. Base url, timeout, params{}, get the api key and set it in the params, to filter out adult films: includes_adult false, certification country, 
2. in the homepage, add the onmounted() to bring in what you want added as soon as the page loads. Also be sure to import the logger.
3. add the movie service class, export const, async getmovies() {const res = await movieapi.get('discover/movie')}
4. copy object from the network, then bring the object into the model and write out the information the api uses for our model. for the background image of the api, string interpolate and bring in the prefix of the url, then interpolate data.x_path. 
5. in the service, add the appstate to the getMovies(). don't forget to map. use . notation to dig in deeper to find the array needed for mapping. 
6. Set up the appstate
7.  in the homepage, setup the computed for movies to bring the information from the appstate. 
8. hardcode in the page to setup how you want it to look in the template. imports always come into the script tag. 
9. build the moviecrd component. add the prop to the card to bring. 
10. in the homepage, bring the movie card and prop over to the template to show the movie image. 
11. add the router-link to have the functionality for the next page. then add a path for th edetails in the router. then add the pathing in the router link to guide the movie path.
12. new moviedetailspage. wetup async function, then try catch pop, under try do the const movieid. 
13. int he service, add teh get moviebyid function to find the details page
14. in the moviedetailspage, add the computed under the return to get the information and post it to thepage. also add information from the model to display to the page
15. build the search function for the website. in the searchbar component, async searchmovie() to build the funcitonality. the look of the bar is up in the template. 
16. to handle the search, in the componene,t const searchterm = ref('') under setup. 
17. in the service, async searchmovies.
18. in the appstate, adding the current page to change functionality between the main page and the search page. appstate.currentpage = res.data.page
19. added total and current pages tothe homepage.
20. homepage, added change page 

<!-- SECTION Thursday, June 1st -->
* beforeEnter: authGuard: before you can get to the account, you need to be logged in. if they're authenticated, let them in. if not, kick them out. 
* scoped in the style tag - this css will only affect this page. 
* try to keep the pages and components 100-150 lines of code. 
* watchEffect() works similarl to a computed, but instead watches for changes then reruns the page. 
* : binding only works on a specific element, v-model is used for forms. 
* if you put in a router-link that doesn't match anything in the router, it breaks everything and crashes. make sure your links are routed.

1. get the stuff - bearer token from sandbox.codeworks. Paste into the env. 
2. open the account page since that's where things will be edited. inspect, network, fetch, preview for all the items that come with the account. 
3. added this.bio, coverimg, social platform & resume to the acount component.
4. in the account page, coverimg computed(() => 'url${appstate stuff}'), backgroundimg v-bind binds the cover image and will show the image better.
5. in the account page, build out the template to design the layout of the account page.  added account-picture in the scss to shape the sizing of the account image. use the v-if for conditionals to show or hide things based on if they have criteria to be hidden or not. 
6. new component accountform - form @submit for the new form. in the return, account: computed(() => appstate.account) to import it from the appstate. then back on the account page, you can brin gin the <accountpage />
7. in the account form, make the editable under the setup then return the edtiable. ref(appstate.account) gives the startpoint for the account edit. place the editable in the form ip above. v-model to bind. 
8. watcheffect - edtiable.value = ...appstate.account & handle submit for the form toto work properly and not update as you type on the page. 
9. in the account form after building the template in that component, give the button some functionality. 
10. in th account service, add the async edit account from the accountForm. appstate.account = new account
11. in the homepage, get rid of the stuff in the template first. then build a projects model in the components and build a projects service.
12. build out the getprojects in the service. build out the template in the homepage to bring the projects forward. then the template inthe project card to build the layout of each card. then build out the image sizing in the projectcard style.
13. build out the modal in the app.vue and add @click in the projectcard to make it an active project. then setactiveproject in the projectcard. import the active project into the appstate. 
14. build the profile page. in the profile page, build out the setup, const route, async getprifle, try catch pop, 
15. build the profile service to retrieve the active profile. import the logger. build the profile card then go from there.

<!-- STUB Fireside with the pokedex. USEFUL STUFF HERE -->
1. pagination: do an @click on the buttons. home page line 3 in the example. the @click funciton is written down below the return. await the service, changepage(), async in the pokemon service.


<!-- SECTION Monday, June 5th & Tuesday, June 6th -->
<!-- STUB back end with Mick-->
1.  Opened up PostMan. 
2. built project in express-vue. project name. click the button to enter the workspace.
3. setup env & env.js & start the server. open local host.
4. to make sure the front and back ends are connected, log in.
5. built the model in the model. export const AlbumSchema = new schema(). build out the properties of the schema.
6. build an album controller and an albumservice. register the model in the DbContext. build out the class & export service for the album service. 
7. export class albumscontroller extends basecontroller in the albums controller. constructor - super. 
8. in the controller, under router, add .post this.create. make sure you're logged in with .use, auth0provider.
9. in the controller still, async create, rrn, try catch next, const album. return res.send. create req.body to make sure the user is the only one who can make an album under their name. 
10. in the albumsservice, add create. const. await album. return album. 
11. in the controller, added .get findallalbums. .get findalbum. asy;nc findallalbums. try catch next. const albums. return res.send. async findalbumbyid. req res next.
12. in the service, add findalbumbyid, const albums. return albums. fidnallalbums const albums. return albums.
13. in the controller, .delete. build async archivealbum, rrn, try catch next, const album, return res.send.
14. in the service, async archiveAlbum, const album, album.archived,  await album.save, if(album.creatorId != userId) throw forbidden.
<!-- STUB still back end, but now for picture things -->
15. create the picture.js model schema. import. export. add details for the schema. don't forget timestamps and toJson. 
16. add pictures to the dbcontext. 
17. create new picturescontroller & pictureservice. in the service, add class & export.
18. in the controller, export extends, import, constructor, super, this.router, async create rrn, try catch next, const picture await, return res.send,
19. in the service, .post &  class pictureservice, const await, pictureData, return picture, 
20. in the service, under createpicture, don't forget to populate the info. 
21. in the ALBUMS controller, add .get(albumId), aasync findAlbumPictures, rrn, try catch next, const await, 
22. in the PICTURES service, add findalbumpictures, const await pictures. find
<!-- anytime you're searching for items, you need to populate -->
<!-- STUB Day 2 with Sam on the front side -->
* first thing you always want to do is build out the .env & the env.js as needed. 
* Account = logged in user and their object is returned from the server. 
* Under the account model, the stuff in extends is hidden except for the user. Everything under profile is what's shown on their main profile. 

1. start off running npm i if you're pulling from a partner. doing the bcw create installs that.
2. double check the server is running if you're cloning the project from your partner or starting it after closing it. 
3. build out the model for the first item. in lecture, starting with the album.
4. lin the account model, add an extends for the profile. 
5. build out the rest of the models that are needed.
6. Build out the services as they're needed. Starting wtih the album service here.
7. in the Homepage, async function getAlbums*(), try catch pop, logger, await albumsService.getalbums(), onMounted getAlbums under catch
8. in the albumsservice, async getalbums(), const res = await api.get(api/albums), logger, 
9. in the appstate, new albums collection, leave it as an empty array.
10. back to the albumservice, appstate.albums, res.data.map(new album stuff), 
11. on the homepage, under return, albums: computed (appstate things), then {{albums}} on the template to make sure the data draws. 
12. on the homepage, rough skeleton to build out the layout of the page. div, con fluid, row*3, label the rows as they are. in the all albums, img, div p with the title, p with the number of likes, i for the like icon, img-fluid, style a bit as needed.
13. grab the template from the album card, cut it out, make a new album card component, vt, then paste it into the template. 
14. back to the homepage, <albumCard />, then build the v-for in the COLUMN NOT THE ROW or it'll make a new row each time. v-for a in albums, :key=a.id, 
15. back int he albumcard, props under the export before setup, album:{ type: Album required true}
<!-- NOTE because the type is being passed through the client side, it's not an object. We've labeled the object as a name for our side, so that's where the type: Album comes in -->
16. back to the homepage bind album with :album="a"
<!-- NOTE with binding, after the bound albumcard, the word following the : bind is what references that word within that component. -->
17. back in the albumcard, change the cover image to the image tag then source album.coverimg. and album.title
<!-- NOTE :alt in the image, is what shows when the image cant' be found. -->
18. if you have a background image, change it in the app.vue to persist across each page. make a class to title the background, then bring in the image. add in the styling to make it look good and work properly. 
<!-- STUB details within the album page -->
19. start with building a new point in the router for the album. don't forget the :id to make sure it's a unique album that's entered.
20. build out the album details page to give the router somewhere to go when the album is clikced on. wrap the router-link around the album card. 
21. in the album details page, import logger and pop. async gealbumbyid, try catch logger pop, asyn getpicturebyalbumid, try catch logger, on mounted  for get album and get pictures.
22. under setup in teh details page, const route = useRoute(), make sure use router is imported, under try, const albumid = route.params.albumid, await albumservice. 
23. in the slbum service, asyn getalbumbyid, const res await, logger.log 
24. make sure to add activealbum to the appstate. 
25. back tothe albumservice, under getalbumbyid, const res await, logger.log, appstate.activealbum, 
26. build a picturesservice so we can get the individual images. class picturesservice export, 
27. back in the album details page, under getpicturesbyalbumid, await picturesservice.getpicturesbyalbumid, const albumId = route.params.id
27/5. make sure to add pictures to the appstate.
28. async getpictuersbyalbumid, const res = await api.get('api/alsdkjflsdjfla'), logger.log, appstate.pictures  = res.data.map(), logger.log
29. build out the template in the albumdetailspage. container fluid, row, col4, col 8, row in the 8, col 6,p, btn, 
30. still on teh detailspage, under return, add the computed for pictures, then back up top for more styling, 
31. build out a modal.vue for funcitonality of the modals and the styling. bring a modal over from boostrap or create your own. get rid of the modal content since we want this to be reusable. add a slot. 
32. in the navbar, add a button to create the album and utilize the modal. 
33. new component to createalbum form. vt for the information. in the template, copy the commented modal content over, then test the opening.
34. bring in the modal under the footer on the app.vue bring in the id to target it, then the createalbumform for the content of the modal, then close the modal.
35. in the createalbumform, finish the form and creating it for each thing that's needed with it. then under the setup, const editable =ref({}), up in the form, write out the v-model. add editable int he return to make it readable by the template. async createalbum, try catch, logger, add the @submit.prevent createalbum, add type submit to the button. add a v-if to the button to make sure it doesn't show up unless there's a user, under the setup, add the user:computed, test.
36. in the fomr still, add const formdata = editable.value, await albumsservice.creataalbum. add a select for the category since that's a requirement of the model and we need to specify what's needed within those options or the album won't post. 
37. in the albumservice, async createalbum(form), cojnst res await, logger, 
38. in the form, add the modal.getorcreateinstance & the editable value to reset the form. create the router object under setup. within the createalbum, add router.push({name:'X', params: {id: newAlbum.id } })
39. within the albumsservice, under createalbum, add return res.data to make sure we have acess to the new page of the album we've just created. 
40. FOR ADDING PICTURES under the previous modal, add another modal calling it createPicture. then add the data-bs-toggle to the button in the ALBUMDETAILSPAGE. 
41. create a new comopnent for creatingpictureform. vt. export setup return under script. grab the modal from the modal component, spice it up as needed with the information that's needed. grab the input from the albumform, add the @submit.prevent, add const editable, async creatpicutre, try catch pop, logger, return editable, in the APPVUE add the createpictureform in the modal, back in the PICTUREFORM, await picturesservice, const formdata = editable, under setup, conf route, then under createpicture, formdata .albumid = route.parmas.id, appstate.pcitures.push, 
42. int he picutresservice, async creatpicture, const res = await api.post, loggger,   
<!-- STUB back side stuff with mick. -->
43. create the collaborator SCHEMA on the server side within the model. export const schema, const objectid, then build everything out under the schema. don't forget the timestamp & the json, 
44. add collaborator to the dbcontext
45. create a collaborator controller & service. within the SERVICE, export const & class. within the CONTROLLER, export class, constructor, super, this.router, .use auth0, .post thiscollaboration, async createcollaboration, rrn, try catch next, const collab, return res.send, req.body.accountId.
46. within the collaborator service, createcollaboration, const collab await dbcontext, return collab, await collab.populate
47. within the ALBUMCONTROLLER, add.getcollaborators under this.router, async findalbumcollaboorators, rrn, try catch next, const collabs await collabservice find albumcollabs(req.params.albumid), return res.send(collabs),
48. within the COLLABSERVICE, findalbumcollabs, const collabs = await colla.find({albumId: albumId}).populate(profile),
49. within the ACCOUNTCONROLLER, .get collaborators, async getaccountcollaborations, rrn, try catch next, const collabs await collabservice, return res.send, 
50. within the COLLABSSERVICE, getaccountcollabs, const collabs = await, accountId, .populate('album'), return collabs
51. async getcollabs, const ocllabs await dbcontext, return collabs, 
52. in teh COLABCONTROLLER, async remove collab, rrn, try catch next, const message collabsservice. removecollab, colalbid userinfo.id, return res.send message, 
53. WITHIN COLLABSERVICE, remvoe collab(collabidk useridk), if x2, await colab.remove(), return collab.id
54. for the count, add the albumschema.virtual member count within the album.js.
55. within the albumsservice, add memberCount to all instances with creator in populate. 
<!-- STUB back to front side with SAM -->
56. setup the buttons for filtering. 
57. on the hOMEPAGE under setup, const filterBy = ref(''), pout @click filterby on each of the buttons, add filterby under return, 
58. build out the collabsservice, class, export const, async getmycollabs, const res - await api.get, logger
59. in the AUTHSERVICE, await ocllabservice.getmycollabs(), 
60. add mycollabs to the appstate then build the model for collabs, export constructork, this / data, 
61. within COLLABBSERVICE, add to getmycollabs, apppstate.mycollabs, logger, 
62. withn ALBUMCARD add the member.count & and in the ALBUMDETAILSPAGE, also in that page,  async function getcollabsbyalbumid, try catch pop, const albumid, await collabservcice, add that functiont onmounted, 
63. in COLLABSSERVICE, async getcollabsbyalbumid, const rest await api.get(api/albums{albumid}h, collabs), logger, asppstate.collabs resdata.map(),  
64. IN ALBUMDETAILSPAGE, add collabs computed, data dump with {{collabs}}, throw in v-for & key on line 36, add an @click to the heart button, async createcollab, trycatch logger, const albumid, 
65. IN collabsservice, async createcollab, const res await api, 
66. in DETAILSPAGE, add iscollaboratoer: computed blah blah blah, async remove collab,  try catch pop await