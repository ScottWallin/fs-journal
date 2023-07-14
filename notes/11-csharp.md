# CSharp

<!-- SECTION June 26 C# stuff -->
* with c#, the variable's types must be declared explicitly. int x = 6. integer x =6. the value of x needs to be declared. 
* float numbers need ot be declared with an f at the end of it.
* double dbl = 12.123d
* decimal = 12.234234589m.
* decimal is the largest number data type.
* string cool = "" string numbers can ONLY be used with double quotes
* char letter = '' letters all require single quotes
* string cooler = $"" for sting interpolation
* bool tru = true
* bool no = false
* bool? nothing = null
int? nada = null
string zero = null "string is the only default null"
* if(variable) doesn't work in c#. you have to write out the full comparison so if(variable == state)
* dictionaries have two data types and they're listed within <> sharks. 
Dictonrary<string(key), string(value)> dict = new Dictionary<string, stirng> {};
dict.Add("one", "anotha one");
dict.Add("two", "anotha one");
dict.Reemove("two");
* class Cat{
  int age
  string name
  public Cat(age, name)
  this.name = name
  this.age = age
}
* PUBLIC name is the constructor 
* List<int> numbers = new List<int>{};
numbers.Add(1)
numbers.Add(2)
numbers.Add(3)
numbers.Add(4)
numbers.Add(5)
numbers.Remove(6)
List<int> lowNumbers = numbers.FindAll(n => n <= 3)
int five = numbers.Find(n = n == 5)
* lists don't have lengths, they have counts. for (int i = 0; i < numbers.Count; i++)
  console.WriteLine($"i:{i} n:{numbers[i]}")
when using names with dotnet, don't use - cus it'll get super mad.
* PUBLIC is an accessor. Allows the accessibility of the field or property. anyone can get or set it. 
* : is the same as extends
* USING = C#'s import/export
* _ in front of something to signify it's private readOnly

<!-- 1. dotnet-auth, name, cd . file name, dotnet restore to make sure dependencies are there. -->
<!-- 2. comment out in Startup.cs ConfigureAuth(services) -->
<!-- 3. reopen it to bring the run and debug info. don't do add configuration. -->
<!-- 4. create new model. IN C# TO IMPORT / EXPORT THE CLASSES NEED OT BE DEFINED IN NAMESPACES. Namespace catRoundUp.Models; (needs to be defined) public class Cat{
  string mame, get/set, public int Age get/set, public string color get/set, public bool LongHair get/set, public bool Penned get/set. On the class name, cmd/ctrl . generate constructor. -->
5. go to controller and build a new one. namespace catRoundUp.Controllers; public class CatsController : ControllerBase, [ApiController], [Route("api/cats")], 
6. define the METHOD. public ActionResult<string> Test() { return "hey";} [HttpGet] up above, try catch. 
<!-- Return needs to be an action request. not just a "string message" but -->
return Ok("string"), under catch , return BadRequest ("I can't do that")
7. within the yellow on the catcontroller, [HttpGet], public ActionResult<List<Cat>>, try catch, catch Exception e, return BadRequest e.Message, under try List<Cat> cats = catsService.getallcats(), return Ok(cats), private readonly CatsService catsService,
8. new catsService.cs, public List<Cat> GetAllCats(), List<Cat> cats = , return cats;
private readonly 
9. new CatsRespository, public class CatsRepo, internal List<Cat> Getallcats(), throw new NotImplementedException(), add dbCats to the places it shows in the example, build fake db things, return dbCats
10. in the Startup, service.AddScoped<CatsService>(); the controller doesn't need to be added. it's looking ot the service, so only the service needs added.
11. httpPost, public ActionResult<Cat> CreateCat([FromBody] Cat catData ), trycatch, Cat cat = catsService.CreateCat(catData
12. in the service, createCat, Cat cat yada yada
13. add createCat to the repository
14. n the model, add the Id to be used for unique pulls.
15. in the controller, [HttpDelete("{CatId}")] public ActionResult<sting> RemoveCat(int catId), try catch, string message = _catsService.removecat(catId)
16. in the service, RemoveCat, follow the rest
17. in the controller, httpPut catId, public actionresult cat, updateCat int catid, fromBody cat updateData, then follow under the try catch
18. in the service, internal cat updatecat(cat updateData), cat original = _repo.getbyid(updatedat.id); if (original == null) throw new excpetion($"no cat at id:{updateData.id}"), original.Age = updateData.Age != null ? updateData.Age : original.Age; repeat for the rest
<!-- SECTION June 27 lecture -->
* table works like a schema
* when doing insert, values to be inserted must be explained.
* var char - variable character - allows max byte size for that column
* @ uses variable by that name so dapper can get the value when it's used. wouldn't be able to otherwise. 

1. start with dbSetup sql
2. create penguin Table within the setup. 
3. insert information in.
4. in database extension, new connection, Name can be whatever. host is master connection endpooint (copy from site), username is sgroot (super general root), paste, name of database (must match what's on the scalegrid.io)
5. in the connection string, bring the stuff over and reference mick's, 
6. build out the model with the same information as the dbsetup. car model for today's example.
7. next, build the carscontroller witht he route
8. in the carsservice, build out the documentation to communicate with the repo. line 10
9. go to startup, add services.addscoped carsrepository & service.
10. cars repo, private readonly idb connection , generate constructor
11. in teh controller, write the get function. public actionresult list car, getallcars, try catch, list car cars carsservice, ok cars
12. in the carsservice, internal list car getallcars, list car/s, erpo get, return,
13. within the repository, under getallcars, string sql = "select * from cars;"; (DONT SAVE), listcar cars = _db.query<car>(sql).tolist(); return cars; (THE THING IN THE CARROT IS SO THAT DAPPER KNOWS WHAT TO RETURN)
14. in the controller, build out the get one car. starting line 28 for ref. httpget, {carId} to pull the number of the id, not have it be an endpoint for the api,
15. in the car repo, getbyid, within the select, string interpolate to get the single car by id.
16. under the controller create car
17. then in service, create car, bring in the carData,
18. in the repo, createcar too. @ in front of strings makes it multiline so it doesn't do one long string. INSERT INTO to add things to the table.  
19. in the controller, htttpdelete, make the result a string to return the "deleted" message. 
20. in the service, add the remove. make sure the car exists first.
21. in the repo, buiold out the delete. delete & no *
22. for the edit, int he controller, httpput, action result, update, try catch
23. in the service, update car, get original, check auth, add the editables, 
24. in the repo, build out the updated car. internal void things. 

<!-- SECTION June 28 -->
* for creatorID in this example, but make sure when you reference another table, they match exactly. id MUST = creatorId in this example because of what it references.
* foreign key restraitng: ties two tables together. Foreign Key: (SETS IT UP) (this thing) references tablename(thing)
* when deleting from the table, use the id but that id is the placement of the thing. when deleting from the account table, use the actual id string.
* in the foreign Key you can add a hook. "on delete cascade" means when the thing is deleted it sends everything else associated with that account
* foreign key IS NOT a virtual creation. to join two tables, SELECT title, name FROM albums JJOIN accounts. this joins both tables and receives information from both.
* async is used in this one to communicate with Auth0 to make sure there's someone logged in. 
* execute returns the amount of rows that were affected.

1. starting with dotnet-vue so we can have our project spun up and retrieve tokens.
2. add all the things in the appsettings.
3. in the dbSetup, created the table. Create Table (name), then add the information.
4. create the insert into with the information from the table.
<!-- STUB create album -->
5. start within the model. namespace then public class. 
6. within the CONTROLLER, namespace, api, public class, rpvate readonly, public repo, httppost, try catch, we alos bring in the private readonly of Auth0 
7. within the STARTUP add the addscoped services & repo
8. within the SERVICE, namespace, public class, private readonly, public repo. When wirting the return under create, the query needs to return the things. the first two are the things it'll pull, but the third is what it'll rturn.
<!-- STUB GET ALBUM -->
9. in the CONTROLLER httpget, actionresult, list, trycatch
10. in the SERVICE, internal list, list albums, getallalbums
11. in the REPO, internal list getallalbums, list albums, 
<!-- STUB get by id -->
12. in the SERVICE internal album getbyid album album, if album
13. in the REPO, internal getbyid, firstordefault since it's not an album
<!-- STUB delete -->
14. in the CONTROLLER, httpdelete, authorize, piblicaction result, try catch return, album album, albumsservice.archivealbum(albumid, userinfo.id)
15. in the SERVICE, internal album archivealbum, album album getbyid, if(album.creatorid != userid), 
16. in the REPO internal void updatealbum, UPDATE albums SET then set all properties to be set, execute sql, 

<!-- SECTION Jun 29 -->
* 
<!-- STUB create pictures -->
1. dbsetup to start making the table first. when referencing id's from other tables, respect the data type. keep it the same. 
2. within the model, build out the pictures model to match the table. the VIRTUAL is made in the model, not the table. reference the picture model if needed for understanding.
3. REPO layer is more or less the main dependent of the three. Starting with REPO layer. namespace, public class pic repo, private readonly, idbconn. cmd + . for the constructor. 
4. SERVICE layer. namespace, public class, private readonly, SERVICE LAYER SHOULD ONLY BE TALKING TO ONE REPO.
5. CONTROLLER layer. namespace, [api], [route], public class, private readonly, public pictures controller, [httppost], [authorize], public ActionResult<Picutre> createpicture(from body for the request body, Picture so we know what object, banana pictureData), pic newpic = picservice.createpic(picdata), wrap the result in a TASK, 
6. SERVICE layer, internal Picture createpc, return repo. RETURN FROM REPO IS NEEDED FOR A SINGLE LINE
7. REPO layer, internal pic creaepic, string sql =@"then insert into table. then insert the data we need. next for values. " adding x.* pulls everything from that table. pulling x.id = last inesert id pulls the most recently uploaded. WHAT COMES AFTER INTERNAL IS WHAT'S RETURNED, pic, pic,
8. in the STARTUP, add the scoped for repo and service. 
<!-- STUB get pictures -->
9. to pull the pictures, go to the ALBUM CONTROLLER because we want to pull them through the albums. httpget albumid/pics, public actionresult list (list because we want lots of them), getpicsbyalbumid, GO TO THE TOP TO BRING IN THE PICTURESSERVICE DEPENDENCY 
10. to the PICTURES SERVICE now to build out the get. internal list pic getpicsbyalbumid int albumid, list pics pics repo
11. to the PICTURES REPO, string sql = @"", list<pic> pics db query pic, act, pic, sql pic act => pic.cre = act, return, new to list
<!-- STUB delete pictures -->
12. in the PIC CONTROLLER httpdelete, auth, public action result, delpic(int pic), try catch, things that i spaced typing in the example today.
13. in the PIC SERVICE internal void del pic, WRITE OUT THE GET BY ID FIRST 
14. in the PIC REPO, WRITE OUT THE GET BY ID, 
15. back to the PIC SERVICE, internal void del pic, such and such. 

<!-- SECTION collaborators -->
<!-- STUB create collabs -->
1. in the SETUP create table if not exists collabs, build out collab table. make it. execute. win.
2. insert into to test it. select from join on join
3. build out the collab model, public class collabacct : acct to extend the account
4. create a COLLAB REPO, namespace, public class, priv readonly, 
5. create a COLLAB SERVICE, namespace, public class, priv readonly,
6. create a new COLLAB CONTROLLER, namespace, apicontroller, route, public calss, private readonly c service & riv readonly auth0, public collabscontroller, 
7. still in CONTROLLER, public actionresult collab create collab from body 
8. in the COLLAB SERVICE, internal create collab
9. in the COLLAB REPO, internal collab createCollab, string sql =@"insert inot, values, ", int id, execute scalar, (SCALAR EXPECTS INFORMATION AND THAT'S WHAT IT'S USED FOR. PULLS MULTIPLE CELLS OF INFO)

<!-- SECTION finishing allspice with sam -->
* 
<!-- STUB get collabs from album -->
1. albums CONTROLLER, grouped with the other gets. httpget{albumid}/collaborators. public actionresult, try catch, build out a new dependency for the collaborators service. we need the service for that one, cus we can't go through the other services.
2. in the collabsCONTROLLER, get them by albumid
3. in the collabs REPO, query to get the information we want, then dapper to map it out.
4. i can't focus this week to save my life. in the collab REPO, getmy collaboratoralbums. 