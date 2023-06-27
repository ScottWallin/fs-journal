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
