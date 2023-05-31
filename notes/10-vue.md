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