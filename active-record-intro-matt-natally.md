Add five family members into the Person table in the Rails console.
Person.create(first_name:'Matthew', last_name:'Munoz', phone:'888-8
88-8888')
Person.create(first_name:'Parker', last_name:'Munoz', phone:'777-77
7-7777')
Person.create(first_name:'Enrique', last_name:'Munoz', phone:'555-5
55-5555')
Person.create(first_name:'Roxanne', last_name:'Munoz', phone:'444-4
44-4444')
Person.create(first_name:'Zoey', last_name:'Munoz', phone:'333-333-
3333')

Retrieve all the items in the database.
Person.all
[#<Person:0x00007f7cb26bf1a8                                  
  id: 1,                                                      
  first_name: "Matthew",                                      
  last_name: "Munoz",                                         
  phone: "888-888-8888",                                      
  created_at: Thu, 12 Jan 2023 19:42:15.001124000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:42:15.001124000 UTC +00:00>,
 #<Person:0x00007f7cb26bf040                                  
  id: 2,                                                      
  first_name: "Parker",                                       
  last_name: "Munoz",                                         
  phone: "777-777-7777",                                      
  created_at: Thu, 12 Jan 2023 19:43:59.837304000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:43:59.837304000 UTC +00:00>,
 #<Person:0x00007f7cb26bef78
  id: 3,
  first_name: "Enrique",
  last_name: "Munoz",
  phone: "555-555-5555",
  created_at: Thu, 12 Jan 2023 19:44:49.588594000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:44:49.588594000 UTC +00:00>,
 #<Person:0x00007f7cb26beeb0
  id: 4,
  first_name: "Roxanne",
  last_name: "Munoz",
  phone: "444-444-4444",
  created_at: Thu, 12 Jan 2023 19:45:19.356448000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:45:19.356448000 UTC +00:00>,
 #<Person:0x00007f7cb26bede8
  id: 5,
  first_name: "Zoey",
  last_name: "Munoz",
  phone: "333-333-3333",
  created_at: Thu, 12 Jan 2023 19:46:09.522951000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:46:09.522951000 UTC +00:00>]

Add yourself to the Person table.
Person.create(first_name:'Natally', last_name:'Quintero', phone:'22
2-222-2222')

Retrieve all the entries that have the same last_name as you.
Person.where last_name:'Munoz'

Update the phone number of the last entry in the database.
natally = Person.find 6
natally.phone = '111-111-1111'
 => "111-111-1111" 
natally.save

Retrieve the first_name of the third Person in the database.
Person.find 3
Person.where first_name:'Enrique'

Stretch Challenges

Update all the family members with the same last_name as you, to have the same phone number as you.
Remove all family members that do not have your last_name.