As a developer, I have been tasked with creating a database model that will be used in a rolodex application. I want to ensure that the database behaves as expected and the necessary actions can be performed on the database instances.

Set Up

Create a new Rails app named 'rolodex_challenge'.
Create the database. The output in the terminal should look like this:

rails new rolodex_challenge -d postgresql -T

Created database 'rolodex_development'
rails db:create
Created database 'rolodex_test'
rails db:create
Generate a model called Person with a first_name last_name, and phone. All fields should be strings.

rails generate model Person first_name:string last_name:string phone:string

Run a migration to set up the database.

rails db:migrate 

Open up Rails console.

rails c

Actions

Add five family members into the Person table in the Rails console.
Person.create(first_name:'Winry', last_name:'Yutig', phone:'iphone')

Retrieve all the items in the database.

Person.all
Add yourself to the Person table.
Person.create first_name:'Romeo', last_name:'Yutig', phone:'iPhone'

Retrieve all the entries that have the same last_name as you.

Person.where last_name:'Yutig'

Update the phone number of the last entry in the database.

romeo.phone='android'
android" 
romeo.save

Retrieve the first_name of the third Person in the database.


Stretch Challenges
Update all the family members with the same last_name as you, to have the same phone number as you.
Remove all family members that do not have your last_name.

ricky=Person.find 2
ricky.destroy
winry=Person.find 1
winry.destroy
petey=Person.find 5
petey.destroy