# SQL
<!-- SECTION Jul 10 notes w/sam -->
* ACCOUNT should only refer to the person logged in. 
* public class ACCOUNT : PROFILE makes account extend profile, with the private information stored within profile. 

1. when building the tables, start with parent. album then picture. recipe then ingredient. cult then cult member.
2. CONTROLLER > SERVICE > REPO
<!-- SECTION Jul 12 w/JAKE -->
* START BY OPENING BACK END THINGS to get the back end to spin up
* If you make a change to the table, make sure you add the change to the model as well. Without that, it won't pull the information.
* for an optional field, default isn't really needed. just make it NULL.
* boolean = BOOLEAN or TINYINT false = 0 true = 1. TINYINT is the better way to go.
* for safety, drop the many to many first.
* FOR EACH TINY CONTROLLER THING, BACKEND, POSTMAN, FRONT END.
* Query AUTOMATICALLY maps to a list
* Restaurant restaurant = var restaurant
* block out by what's needed first. The ability to create restaurants and view them. the router to see them. the ability to see reviews on the pages & on your account page. start with the requirements.
* <SCRIPT SETUP> puts us right inside the setup. we're already in the setup now.
* Build as you go. Don't build the entire thing first.
* starting: REPO -> SERVICE -> CONTROLLER -> SERVICE -> REPO
* 

1. 