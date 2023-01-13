Add five family members into the Person table in the Rails console.
Retrieve all the items in the database.
Add yourself to the Person table.
Retrieve all the entries that have the same last_name as you.
Update the phone number of the last entry in the database.



Last login: Wed Jan 11 10:33:56 on ttys000
➜  rolodex_challenge git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > code .
3.0.0 :002 > cd .. 
(irb):1:in `<main>': undefined local variable or method `code' for main:Object (NameError)                                           
3.0.0 :003 > exit
➜  rolodex_challenge git:(main) ✗ code .
➜  rolodex_challenge git:(main) ✗ ruby c
ruby: No such file or directory -- c (LoadError)
➜  rolodex_challenge git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > exit
➜  rolodex_challenge git:(main) ✗ rails generate model Person first_name:string last_name:string phone:strings  
Could not generate field 'phone' with unknown type 'strings'.
➜  rolodex_challenge git:(main) ✗ rails generate model Person first_name:string last_name:string phone:string
      invoke  active_record
      create    db/migrate/20230112193236_create_people.rb
      create    app/models/person.rb
➜  rolodex_challenge git:(main) ✗ db:migrate
zsh: command not found: db:migrate
➜  rolodex_challenge git:(main) ✗ rails db:migrate
== 20230112193236 CreatePeople: migrating =====================================
-- create_table(:people)
   -> 0.0070s
== 20230112193236 CreatePeople: migrated (0.0070s) ============================

➜  rolodex_challenge git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Person.all
  Person Load (1.0ms)  SELECT "people".* FROM "people"
 => []                                                        
3.0.0 :002 > Person.create first_name: "Octavio", last_name: "sifuentes", phone: 1
234567891
  TRANSACTION (0.2ms)  BEGIN
  Person Create (0.7ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Octavio"], ["last_name", "sifuentes"], ["phone", "1234567891"], ["created_at", "2023-01-12 19:41:15.330435"], ["updated_at", "2023-01-12 19:41:15.330435"]] 
  TRANSACTION (0.4ms)  COMMIT                                                     
 =>                                                                               
#<Person:0x0000000114977718                                                       
 id: 1,                                                                           
 first_name: "Octavio",                                                           
 last_name: "sifuentes",                                                          
 phone: "1234567891",                                                             
 created_at: Thu, 12 Jan 2023 19:41:15.330435000 UTC +00:00,                      
 updated_at: Thu, 12 Jan 2023 19:41:15.330435000 UTC +00:00>                      
3.0.0 :003 >  Person.create first_name: "Octavio", last_name: "sifuentes", phone: 
1
  TRANSACTION (0.1ms)  BEGIN
  Person Create (0.3ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Octavio"], ["last_name", "sifuentes"], ["phone", "1"], ["created_at", "2023-01-12 19:42:47.292628"], ["updated_at", "2023-01-12 19:42:47.292628"]]
  TRANSACTION (5.2ms)  COMMIT                
 =>                                          
#<Person:0x0000000130e434d8                  
 id: 2,                                      
 first_name: "Octavio",                      
 last_name: "sifuentes",                     
 phone: "1",                                 
 created_at: Thu, 12 Jan 2023 19:42:47.292628000 UTC +00:00,
 updated_at: Thu, 12 Jan 2023 19:42:47.292628000 UTC +00:00> 
3.0.0 :004 > person.find(2).destroy
(irb):4:in `<main>': undefined local variable or method `person' for main:Object (NameError)                                                                        
3.0.0 :005 > Person.find(2).destroy
  Person Load (0.3ms)  SELECT "people".* FROM "people" WHERE "people"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]                                                 
  TRANSACTION (0.1ms)  BEGIN                                                      
  Person Destroy (5.5ms)  DELETE FROM "people" WHERE "people"."id" = $1  [["id", 2]]                                                                                
  TRANSACTION (0.4ms)  COMMIT                                                     
 =>                                                                               
#<Person:0x00000001139e0200                                                       
 id: 2,                                                                           
 first_name: "Octavio",                                                           
 last_name: "sifuentes",                                                          
 phone: "1",                                                                      
 created_at: Thu, 12 Jan 2023 19:42:47.292628000 UTC +00:00,
 updated_at: Thu, 12 Jan 2023 19:42:47.292628000 UTC +00:00> 
3.0.0 :006 > person.all
(irb):6:in `<main>': undefined local variable or method `person' for main:Object (NameError)                                                                   
3.0.0 :007 > Person.all
  Person Load (0.4ms)  SELECT "people".* FROM "people"
 =>                                                                          
[#<Person:0x0000000111999a00                                                 
  id: 1,                                                                     
  first_name: "Octavio",                                                     
  last_name: "sifuentes",                                                    
  phone: "1234567891",                                                       
  created_at: Thu, 12 Jan 2023 19:41:15.330435000 UTC +00:00,                
  updated_at: Thu, 12 Jan 2023 19:41:15.330435000 UTC +00:00>]               
3.0.0 :008 > Person.create first_name:ney, last_name:vencer, phone:2345678912  
(irb):8:in `<main>': undefined local variable or method `ney' for main:Object (NameError)                                                                           
Did you mean?  next                                                               
3.0.0 :009 > Person.create first_name:"ney", last_name:vencer, phone:2345678912  
(irb):9:in `<main>': undefined local variable or method `vencer' for main:Object (NameError)                                                                        
3.0.0 :010 > Person.create first_name:"ney", last_name:"vencer", phone:"2345678912
"  
  TRANSACTION (0.2ms)  BEGIN
  Person Create (0.3ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "ney"], ["last_name", "vencer"], ["phone", "2345678912"], ["created_at", "2023-01-12 19:46:56.097516"], ["updated_at", "2023-01-12 19:46:56.097516"]]        
  TRANSACTION (5.0ms)  COMMIT                                                     
 =>                                                                               
#<Person:0x00000001330e9de8
 id: 3,
 first_name: "ney",
 last_name: "vencer",
 phone: "2345678912",
 created_at: Thu, 12 Jan 2023 19:46:56.097516000 UTC +00:00,
 updated_at: Thu, 12 Jan 2023 19:46:56.097516000 UTC +00:00> 
3.0.0 :011 > Person.all
  Person Load (0.4ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x0000000114987b68                                  
  id: 1,                                                      
  first_name: "Octavio",                                      
  last_name: "sifuentes",                                     
  phone: "1234567891",                                        
  created_at: Thu, 12 Jan 2023 19:41:15.330435000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:41:15.330435000 UTC +00:00>,
 #<Person:0x0000000114987aa0                                  
  id: 3,                                                      
  first_name: "ney",                                          
  last_name: "vencer",                                        
  phone: "2345678912",                                        
  created_at: Thu, 12 Jan 2023 19:46:56.097516000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:46:56.097516000 UTC +00:00>] 
3.0.0 :012 > Person.create first_name:jeff, last_name:flandders, phone:1738
(irb):12:in `<main>': undefined local variable or method `jeff' for main:Object (NameError)                                                                         
3.0.0 :013 > Person.create first_name:"jeff", last_name:"flandders", phone:1738
  TRANSACTION (0.2ms)  BEGIN
  Person Create (0.4ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "jeff"], ["last_name", "flandders"], ["phone", "1738"], ["created_at", "2023-01-12 19:49:21.942525"], ["updated_at", "2023-01-12 19:49:21.942525"]]          
  TRANSACTION (0.3ms)  COMMIT                                                     
 =>                                                                               
#<Person:0x0000000111ab2590                                                       
 id: 4,                                                                           
 first_name: "jeff",                                                              
 last_name: "flandders",                                                          
 phone: "1738",                                                                   
 created_at: Thu, 12 Jan 2023 19:49:21.942525000 UTC +00:00,
 updated_at: Thu, 12 Jan 2023 19:49:21.942525000 UTC +00:00> 
3.0.0 :014 > Person.create first_name:"apple", last_name:"garcia", phone:1234567
  TRANSACTION (0.2ms)  BEGIN
  Person Create (0.5ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "apple"], ["last_name", "garcia"], ["phone", "1234567"], ["created_at", "2023-01-12 19:50:32.958366"], ["updated_at", "2023-01-12 19:50:32.958366"]]         
  TRANSACTION (4.8ms)  COMMIT                                                     
 =>                                                                               
#<Person:0x0000000113b3abc8                                                       
 id: 5,                                                                           
 first_name: "apple",                                                             
 last_name: "garcia",                                                             
 phone: "1234567",                                                                
 created_at: Thu, 12 Jan 2023 19:50:32.958366000 UTC +00:00,                      
 updated_at: Thu, 12 Jan 2023 19:50:32.958366000 UTC +00:00>                      
3.0.0 :015 > Person.create first_name:"fred", last_name:"smith", phone:9876543219
  TRANSACTION (0.2ms)  BEGIN
  Person Create (0.3ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "fred"], ["last_name", "smith"], ["phone", "9876543219"], ["created_at", "2023-01-12 19:51:28.326727"], ["updated_at", "2023-01-12 19:51:28.326727"]]        
  TRANSACTION (0.6ms)  COMMIT                                                     
 =>                                                                               
#<Person:0x00000001141b6218                                                       
 id: 6,                                                                           
 first_name: "fred",                                                              
 last_name: "smith",                                                              
 phone: "9876543219",                                                             
 created_at: Thu, 12 Jan 2023 19:51:28.326727000 UTC +00:00,                      
 updated_at: Thu, 12 Jan 2023 19:51:28.326727000 UTC +00:00>                      
3.0.0 :016 > Person.all
  Person Load (0.4ms)  SELECT "people".* FROM "people"
 =>                                                           
[#<Person:0x0000000130cccb90                                  
  id: 1,                                                      
  first_name: "Octavio",                                      
  last_name: "sifuentes",                                     
  phone: "1234567891",                                        
  created_at: Thu, 12 Jan 2023 19:41:15.330435000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:41:15.330435000 UTC +00:00>,
 #<Person:0x0000000130ccc870                                  
  id: 3,                                                      
  first_name: "ney",                                          
  last_name: "vencer",                                        
  phone: "2345678912",                                        
  created_at: Thu, 12 Jan 2023 19:46:56.097516000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:46:56.097516000 UTC +00:00>,
 #<Person:0x0000000130ccc500
  id: 4,
  first_name: "jeff",
  last_name: "flandders",
  phone: "1738",
  created_at: Thu, 12 Jan 2023 19:49:21.942525000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:49:21.942525000 UTC +00:00>,
 #<Person:0x0000000130ccc0f0
  id: 5,
  first_name: "apple",
  last_name: "garcia",
  phone: "1234567",
  created_at: Thu, 12 Jan 2023 19:50:32.958366000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:50:32.958366000 UTC +00:00>,
 #<Person:0x000000011174bde8
  id: 6,
  first_name: "fred",
  last_name: "smith",
  phone: "9876543219",
  created_at: Thu, 12 Jan 2023 19:51:28.326727000 UTC +00:00,
  updated_at: Thu, 12 Jan 2023 19:51:28.326727000 UTC +00:00>] 
3.0.0 :017 > Person.where(last_name = "vencer")
  Person Load (2.6ms)  SELECT "people".* FROM "people" WHERE (vencer)
(Object doesn't support #inspect)                             
 =>                                                           
3.0.0 :018 > Person.where last_name: "vencer"
  Person Load (0.4ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "vencer"]]                               
 =>                                                           
[#<Person:0x00000001148d7b78                                  
  id: 3,                                                      
  first_name: "ney",                                          
  last_name: "vencer",                                        
  phone: "2345678912",                                        
  created_at: Thu, 12 Jan 2023 19:46:56.097516000 UTC +00:00, 
  updated_at: Thu, 12 Jan 2023 19:46:56.097516000 UTC +00:00>] 
3.0.0 :019 > exit



Retrieve the first_name of the third Person in the database.
Stretch Challenges





Update all the family members with the same last_name as you, to have the same phone number as you.


Remove all family members that do not have your last_name.
Back to Syllabus