# CLAIMS
#### Video Demo:  <URL HERE>
#### Description:
This is a web page that allows the neighbors to elevate claims for missing manhole cover of the sanitary service or sanitary sewer overflow with the exact direction of the problem.

The user enters the page, fills in the forms with their full name, address of the problem, and then chooses the reason for the claim, which may be Sanitary Sewer Overflow or Missing sewer cover, then search for the place, and if this place found is in the problem address, the user presses "Add claim" and is redirected to a page that gives him a claim number. This button remains disabled until the form is completed.

All claims are received so that the sanitary sewer maintenance agent can resolve them, once they register on the page, selecting a "Username", a "Password" and using a code that only the service agents have, they can see all claims. on a map, differentiated by color, or you can simply see each point of a single complaint reason. In addition, it has a button to delete a resolved claim and all claims can be downloaded in a .csv file.
## Files:
### claims.db:
claims.db the SQLite3 database, wich has two tables, "claims" and "users". The first one has the address of the claim, the claim number, the coords (longitude and latitude)
### login.py: 
Here is the decorator route to require login. [Login Required Decorator](https://flask.palletsprojects.com/en/1.1.x/patterns/viewdecorators/)
### index.html:
This is initial page where the user fill the "Surname and Name", direction of the claim and reason of the claim. With a map centered in Córdoba city, when the user searches a new direction, the map is refreshed with ajax without reloading
the whole page, with a marker added in the place.
