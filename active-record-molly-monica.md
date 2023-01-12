Challenge: Rolodex

As a developer, I have been tasked with creating a database model that will be used in a rolodex application. I want to ensure that the database behaves as expected and the necessary actions can be performed on the database instances.

## Set Up

# Create a new Rails app named 'rolodex_challenge'.
- input: rails new rolodex_challenge -d postgresql -T

# Create the database. The output in the terminal should look like this:
- input: cd rolodex_challenge
- input: rails db:create
Created database 'rolodex_development'
Created database 'rolodex_test'

# Generate a model called Person with a first_name, last_name, and phone. All fields should be strings.
- input: rails generate model Person frist_name:string last_name:string phone:string 

- output:       invoke  active_record
      create    db/migrate/20230112192623_create_people.rb
      create    app/models/person.rb

# Run a migration to set up the database.
- input: rails db:migrate
- output: == 20230112192623 CreatePeople: migrating =====================================
-- create_table(:people)
   -> 0.0104s
== 20230112192623 CreatePeople: migrated (0.0104s) ============================

# Open up Rails console.
- input: rails console
- output: Loading development environment (Rails 7.0.4)
- 3.0.0 :001 > 

## Action

# Add five family members into the Person table in the Rails console.
- 3.0.0 :003 > Person.create(frist_name:'Molly', last_name:'Wolf', phone:'000-0000')
- 3.0.0 :003 > Person.create(frist_name:'Monica', last_name:'Arganda', phone:'000-0000')
- 3.0.0 :009 > Person.create(frist_name:'Ruby', last_name:'Rails', phone:'000-0001')
- 3.0.0 :010 > Person.create(frist_name:'Java', last_name:'Script', phone:'000-0002')
- 3.0.0 :011 > Person.create(frist_name:'React', last_name:'Lucifer', phone:'000-0006')

# Retrieve all the items in the database.
- 3.0.0 :012 > Person.all
  Person Load (0.5ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x000000014710dd88                                  
  id: 1,                                                      
  frist_name: "Molly",                                        
  last_name: "Wolf",                                          
  phone: "000-0000",                                          
  created_at: Thu, 12 Jan 2023 19:32:12.965660000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:32:12.965660000 UTC +00:00>,
 #<Person:0x000000014710d8b0                                  
  id: 2,                                                      
  frist_name: "Monica",                                       
  last_name: "Arganda",                                       
  phone: "000-\n  0000",                                      
  created_at: Thu, 12 Jan 2023 19:33:50.457279000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:33:50.457279000 UTC +00:00>,
 #<Person:0x000000014710d630
  id: 3,
  frist_name: "Ruby",
  last_name: "Rails",
  phone: "000-0001",
  created_at: Thu, 12 Jan 2023 19:34:45.904403000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:34:45.904403000 UTC +00:00>,
 #<Person:0x000000014710d428
  id: 4,
  frist_name: "Java",
  last_name: "Script",
  phone: "000-0002",
  created_at: Thu, 12 Jan 2023 19:36:08.072500000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:36:08.072500000 UTC +00:00>,
 #<Person:0x000000014710d270
  id: 5,
  frist_name: "React",
  last_name: "Lucifer",
  phone: "000-0006",
  created_at: Thu, 12 Jan 2023 19:37:33.463147000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:37:33.463147000 UTC +00:00>] 

# Add yourself to the Person table.
- Person.create(frist_name:'CSS', last_name:'Front End', phone:'000-0004')

# Retrieve all the entries that have the same last_name as you.
- Person.where(last_name:'Wolf')

# Update the phone number of the last entry in the database.
- Person.last.update(phone:'456-3214')
- Person.last

# Retrieve the first_name of the third Person in the database.
- Person.find(3).frist_name

## Stretch Challenges

# Update all the family members with the same last_name as you, to have the same phone number as you.
- Person.where(last_name:'Arganda').update(phone:'234-5432')

# Remove all family members that do not have your last_name.
