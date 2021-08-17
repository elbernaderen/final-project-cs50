# eClaimer
#### Video Demo:  <https://youtu.be/P9GTnk0oI_Y>
#### Description:
This is a web page that allows neighbors to send complaints to send their infrastructure complaints with the exact address of the problem.

The user enters the page, fills in the forms with their full name, address of the problem, and then chooses the reason for the claim, which may be Sanitary Sewer Overflow or Missing sewer cover, then search for the place, and if this place found is  the problem address, the user presses "Add claim" and is redirected to a page that gives him a claim number. This button will remain disabled until the form is completed.
All complaints are received so that the sanitary sewer maintenance agent can track them., once they are registered on the page, selecting a "User Name", a "Password" and using a private code that only service agents have. Agents can view all complaints on a map, differentiated by color, or they can simply view each point of a single complaint reason. In addition, there is a button to delete a resolved claim and all claims can be downloaded in a .csv.
## Requirements:
  Must install the next libraries:
#### Important library for many geopython libraries
!apt install gdal-bin python-gdal python3-gdal
#### Install Folium for Geographic data visualization
!pip install folium
#### Install plotlyExpress
!pip install plotly_express
## Files:
### claims.db:
claims.db is the SQLite3 database, which has two tables, "claims" and "users". The first one has the address of the claim, the claim number, the coordinates (longitude and latitude), date, and name of the claimer. The other one has the username and hash of the password of the agent.
### login.py:
Here is the path to the decorator to require login. [Login required decorator](https://flask.palletsprojects.com/en/1.1.x/patterns/viewdecorators/).
### index.html:
This is the initial page where the user fills in the "Last Name and First Name", the address of the claim and the reason for the claim. With a map centered on the city of Cordoba, when the user searches for a new address, the map is updated with ajax without reloading the whole page with a marker added at the location. The "Add claim" button remains disabled until the form is filled in and the reason is chosen.
### claimed.html:
If the claim has been added, the claim number is indicated on this page.
### register.html:
Here service agents can register on the page by setting a user name, password and the code provided (the user name and password must be longer than 8 characters, or the button will be disabled).
### login.html:
With the chosen username and password, in this html the agent can log in on the receiver side.
### claims.html:
After logging in, in this html the agent can view all claims on a map, differentiated by color, or he can simply view each point of a single claim reason. He can also delete resolved claims and download all claims in a csv file.
### ajax_dir.html:
The options to select the claim address in claims.html after modifying the reason options, is rendered from the server by this html using ajax and javascript.
### map.html:
This is the html made with **save** of folium, which saves the map generated with **folium.Map** and the markers added with **folium.Marker**. Then this html is rendered on the page that requires it.
### get_.html:
The map is rendered in an iframe when required with this html using javascript and ajax.
### del.html:
This html is used to render the id of the deleted claim shown in an alert, using ajax and javascript.
### layout.html:
The common html content in most of these pages are here. Some things are taken from the **CS50 *Finance*** problem, and some content properties are from Bootstrap.

