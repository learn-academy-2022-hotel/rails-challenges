Challenge: Rolodex

As a developer, I have been tasked with creating a database model that will be used in a rolodex application. I want to ensure that the database behaves as expected and the necessary actions can be performed on the database instances.

Set Up

Create a new Rails app named 'rolodex_challenge'.
- input: rails new rolodex_challenge -d postgresql -T

Create the database. The output in the terminal should look like this:
- input: cd rolodex_challenge
- input: rails db:create
Created database 'rolodex_development'
Created database 'rolodex_test'

Generate a model called Person with a first_name, last_name, and phone. All fields should be strings.
- input: rails generate model Person frist_name:string last_name:string phone:string 

- output:       invoke  active_record
      create    db/migrate/20230112192623_create_people.rb
      create    app/models/person.rb

Run a migration to set up the database.
- input: rails db:migrate
- output: == 20230112192623 CreatePeople: migrating =====================================
-- create_table(:people)
   -> 0.0104s
== 20230112192623 CreatePeople: migrated (0.0104s) ============================

Open up Rails console.
- input: rails console
- output: Loading development environment (Rails 7.0.4)
- 3.0.0 :001 > 

Action

Add five family members into the Person table in the Rails console.
Retrieve all the items in the database.
Add yourself to the Person table.
Retrieve all the entries that have the same last_name as you.
Update the phone number of the last entry in the database.
Retrieve the first_name of the third Person in the database.
Stretch Challenges

Update all the family members with the same last_name as you, to have the same phone number as you.
Remove all family members that do not have your last_name.