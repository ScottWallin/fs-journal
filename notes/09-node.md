# Node

<!-- SECTION Monday May, 22 -->
* package.json. looks like a javascript object.
* dependencies are libraries of what we'll be using in our project. "express" is the core library we'll be using while running node.
* mongoose is what we use to talk to our database.
* devDependencies are only there when you're in the environment. they help with writing and double checking your work. They aren't used directly, just running in the background.
<!-- IMPORTANT -->
* to make sure they run: BE IN THE DIRECTORY THAT YOU HAVE A PACKAGE.JSON > RUN NPM I > ENTER > READS YOUR PACKAGE.JSON THEN INSTALLS THE NEEDED THINGS. IT GIVES A .\NODE_MODULES\ FOLDER AND THAT'S THE ONLY PLACE THIS GOES. 
<!-- ///////////// -->
* node doesn't support the elvis operator
* for postman: email, Bullwulfe, usual password
* when making a change to the server, click the green arrow upper right to restart/refresh the server
* request, response, next. req, res, next
* gets and deletes don't have bodies, creates and puts do. 
* ~~ is shorthand for math.floor

1. node-server-auth0 opened in the terminal
2. express
3. npm init -f in the terminal on vscode
4. in package.json: scripts: start, node, index.js
5. go into the env file and paste int he domain, audience, and clientId NO QUOTES OR SPACES
6. localhost:3000/api/values
7. new tigerscontroller
8. export class xcontroller extends basecontroller
9. constructor() > super('api/x')
10. this.router.get('', this.getX)
11. async getX(req, res, next) > try/catch > next(error) > logger.log('xxxxxx' req/res) > res.send('x')
12. save respin


<!-- SECTION Tuesday, May 23 -->
* Auth0:
Auth Domain: dev-ogvwlqpn7yrkw51n.us.auth0.com
Client-ID: kbUYLZFBDzLHWaydCqitqaHcYiAXMld8
API Audience: http://sandbox.com
* You don't want to push only your client or server into GitHub. Fix in step 4.
* Schema: database's word for class/model. interchangeable. 
* schema validation: in my database, you must look like this. those are in the export const of the account schema from today. give an error if those validations aren't met. 
* Mongoose: ODM: Object Data Modeler. Object database - model those objects into something else. Translator between my javascript class and my database schema/model 
* Enumerator: ENUM: other way to set up options for a user. Must be written in a string.
* post and put requests always come in with a body
* query = search. 
* mongoose: argument must be formatted as an object or it won't work
* auth: line 31 on the service to remove access of deleting hte car from anyone except the creator

1. bcw create
2. express-mvc
3. closed vscode, reopened it, initialize before opening the workspace.
4. open up env. copy over the things from the notepad we did today with the domain, client ID, api, connection string, and port 3000
5. copied over everything we did to the notepad that way it can be saved to use for later projects.
6. open up env.js and repeat.
7. bcw serve
8. new car.js model
9. import mongoose / const schema = mongoose.schema
10. export const xSchema = new Schema() { input the data for the model within the brackets.}
11. db > db context > this is where we'll register the schemas/models to the database. within the class: Xs = mongoose.model('X', XSchema)
<!-- left side of = is "AppState" references our local app code. AppState.x. DbContext.(model name) -->
12. XsService.js is built. Add the class, export const.
13. export class XsController extends BaseController brings things from the base controller. 
14. constructor{super('api/xs'), this.router, .get('', this.getXs)}
15. async getXs(req, res, next){ try, catch, next, return res.send() const xs = await xsService.getXs()}
16. in the class, const xs = await dbContext.Xs.find(). return xs
17. new collection in postman. named gregslist. new request: get Xs
18. in the gregslist tab, added the baseURL to the variables to make the main site. then under the cars folder, just added {{baseURL}}/api/cars
19. xscontroller, export class, .use(Auth0Provider.getAuthorizedUserInfo)>.post('', this.CreateX) to make sure someone can't add information unless they're logged in. unless their identity as a user is confirmed.
20. createX(req, res, next), try catch next 
21. add request on postman under the cars folder, added the baseurl bit, copied the user token into th gregslist under variables. 
22. in createX, const xData = req.body, const newX = await xsService.createX(xData), res.send(newX)
23. in xsService, async createX(xData), const newX = await dbContext.Xs.create()
24. in postman, post a body in the X folder, 
25. in controller, .get above the middleman thing to show they can view the cars without needing to be logged in. 
26. in the controller, under the middleman, .put('/')
27. editX(rrn), try catch next, const xData =  req.body, const editedX = await xsService.exitX(), const xId params bit
28. in the service, editX(xData, xId), check first that the thing that's edited exists. const originalX = await this.cetXyId(xId), originalX.model = xData.model || originalX.model OR originalX.make = xData.make ? xData.make : originalX.make
29. add in all the things from the model. for editing booleans, always need to do the null coalescence. be super strict. it's on line 40 of the cars service from today's lecture. > await originalX.save(), return originalX
30. added delted to the top of the controller. 
31. deleteX(rrn), try catch next return, const xId = req.params.xId, return res.send ('x wa deleted)
32. in the service, deleteX(xId), async delteX(xId), const x = await this.getXByID(xID), await x.remove() OR const x = await dbContext.Ds.findByIdAndDelete(xID)

<!-- STUB JORDAN'S KICKASS FIRESIDE -->
1. in the model: export const XSchema = new Schema() & import {X} from "mongoose';
2. make sure you're exporting class, not const, in the controller.
3. constructor: super then this.router then .use(Auth0Provider.getAuthorizedUserInfo) to pull the authorized information.
4. 


<!-- SECTION Wednesday, May 24th -->
* two types of relationships: 1:1, 1:Many, Many:Many
* 1:1 = unique pairing. they exist independently to each other and 
* 1:Many = one collection that goes to many things
* Many:Many = Many things with many things inside them. 
* lucid uml diagram
* with a 404, check the router. 

1. opened express mvc > init publish
2. added the things to the .env file and the env.js
3. build the school schema in the models. import mongoose. const schema
4. added the things into the schema that we got from the lucid diagram.
5. in the dbcontext, added the school model 
6. added the schools controller & service
7. in the service, class schoolsService / export const schoolsservice
8. in the controller, export class schoolscontroller
9. constructor / super. in super('api/schools') this.router
10. added .post('', this.createschool) then create school rrn try catch return / const schooldata / const newschool = await
11. in the service, async create, const newschool = await / return
12. created postman. baseurl setup as the localhost. folder for schools. post. {{baseURL}}/api/xxxx
13. copied over schema to postman. filled out details of the model for the one. send. made a new one.
14. back in the controller, in the constructor added .get('',getschools)
15. getschools(rrn), try catch next, const query = req.query. const schoools = await schoolsservice. res.send(schools)
16. in the service, getschools(query), const school = await.--.find, return schools
17. back to postman. added a get, {{baseURL}}/api/schools
18. back to cotroller, .get('/:id', this.getbyID), created getbyid.
19. getbyid(rrn), try catch next, const schoolid = req.params.schoolid, const school = await schoolsservice.getschoolbyid(schoolid), res.send(school), add the bad request from today's lecture.
20. in the service, getbyid(schoolid), const school = await dbcontext.schools.findbyid(schoolid) OR const school = await dbcontext.schools.find({_id:schoolid})
21. back to postman, new get folder, paste id into the url line
22. still in postman, new folder of courses. create {{baseURL}}
23. new course model. export const courseschema & import mongoose & then add in the data for the course schema. to reference other models, add the {ref: 'model name'}
24. in the model, courseSchema.virtual('school', { localField, 'schoolId', ref: 'school', foreignfield: '_id', justOne: true })
<!-- local field is what's local to where this is -->
25. course cshema to the dbcontext
26. in the coursescontroller, import basecontroller, export class, constructor, super('api/courses'), this.router. .post('', this.createCourse).
27. createcourse(rrn), try catch next, const courseData = req.body, const enwcourse = await coursesservice.createcourse(), return res.send
28. in the service, createcourse, const newcourse = await dbcontext.course.create(coursedata), return newcourse
29. in the postman, copy over the model then add the info.
30. missed a bit. but if you add .get('/:schooolId/courses') helps with the roadmap for the API to layout the endpoints for the api to reference.
31. two virtuals needed when you have multiple id's. in this expample, did coursestudentschema.virtual('course', {localField: 'courseId', ref: 'course', foreignfield:,_id', justone: true}) & coursestudentschema.virtual('student', {localfield: 'accountId', ref:'account', foreignfield: '_id', justone: true}) then register in the database context. dbcontex