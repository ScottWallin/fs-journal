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