To recreate the project:
1. Set up mysql.
   a. Set the username to 'root' and password to 'tajikistan'. The front-end uses these values for the database connection.
   b. Create a database called defaultdatabase.
   c. Copy the query from CreateQuery.md and run it. This will create the tables and views.
   d. Copy the query for DummyDataInsert.md and run it.
     1. There will be a normal user with username 'elliott' and password 'tajikistan'. The user can save sites and leave reviews.
     2. There will be an admin user with username 'adam' and password 'tajikistan'. The admin can create sites and events.
3. Set up the front-end in Mendix.
   a. Download Mendix Studio Pro 10.8.0 or later.
     1. This will require registering to Mendix.
   b. Download the WOOP.mpr file.
   c. Open Mendix Studio Pro, select 'Import App Package' and select the WOOP.mpk file. 
   d. Once loaded, click the play button on the top right of Mendix Studio Pro.
   e. Click 'View App' on the top right of Studio Pro and the website will open in the browser.
4. Test the site.
   a. If not signed in, view the sites, events, and reviews. Can also register.
   b. If signed in, can leave reviews and save sites.
   c. If signed in as admin 'adam' with password 'tajikistan', can do everything the user does as well as create sites and events.
