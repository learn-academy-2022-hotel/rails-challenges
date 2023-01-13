# Actions

- Add five family members into the Person table in the Rails console.
    ```
    3.0.0 :005 > Person.create(first_name:'Charlean', last_name:'Baxter', phone:'555-555-5555')

    TRANSACTION (5.9ms)  BEGIN
    Person Create (0.8ms)  INSERT INTO "people" ("first_name", "last_name", "phone", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["first_name", "Charlean"], ["last_name", "Baxter"], ["phone", "555-555-5555"], ["created_at", "2023-01-12 19:41:32.208033"], ["updated_at", "2023-01-12 19:41:32.208033"]]                                                                         
    TRANSACTION (1.6ms)  COMMIT                                                   
    =>                                                                             
    #<Person:0x00007fa986b99448                                                     
    id: 4,                                                                         
    first_name: "Charlean",                                            
    last_name: "Baxter",                                               
    phone: "555-555-5555",                                            
    created_at: Thu, 12 Jan 2023 19:41:32.208033000 UTC +00:00,                    
    updated_at: Thu, 12 Jan 2023 19:41:32.208033000 UTC +00:00> 
    ```

- Retrieve all the items in the database.
    ```
    Person.all
    ```

- Add yourself to the Person table.
    ```
    Person.create(first_name:'Moss', last_name:'Cantrell', phone:'407-615-9422')
    ```

- Retrieve all the entries that have the same last_name as you.
    ```
    Person.where last_name: 'Cantrell'
    Person Load (0.8ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "Cantrell"]]                           
    =>                                                           
    [#<Person:0x00007fa9895005c0                                  
    id: 2,                                                      
    first_name: "Moss",                                         
    last_name: "Cantrell",                                      
    phone: "407-615-9422",                                      
    created_at: Thu, 12 Jan 2023 19:36:30.017528000 UTC +00:00, 
    updated_at: Thu, 12 Jan 2023 19:36:30.017528000 UTC +00:00>,
    #<Person:0x00007fa9895004f8                                  
    id: 5,                                                      
    first_name: "Timmy",                                        
    last_name: "Cantrell",                                      
    phone: "727-444-4444",                                      
    created_at: Thu, 12 Jan 2023 19:44:36.651966000 UTC +00:00,
    updated_at: Thu, 12 Jan 2023 19:44:36.651966000 UTC +00:00>] 
    3.0.0 :011 > 
    ```

- Update the phone number of the last entry in the database.
    ```
    Person.last.update(phone:'222-222-2222')
    Person Load (0.4ms)  SELECT "people".* FROM "people" ORDER BY "people"."id" DESC LIMIT $1  [["LIMIT", 1]]                                                     
    TRANSACTION (0.2ms)  BEGIN                                                    
    Person Update (0.5ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "222-222-2222"], ["updated_at", "2023-01-12 19:56:32.416288"], ["id", 5]]                                                     
    TRANSACTION (0.8ms)  COMMIT                                                   
    => true           
    ```

- Retrieve the first_name of the third Person in the database.
    ```
    3.0.0 :018 > Person.third.first_name
    Person Load (8.6ms)  SELECT "people".* FROM "people" ORDER BY "people"."id" ASC LIMIT $1 OFFSET $2  [["LIMIT", 1], ["OFFSET", 2]]                             
    => "Oscar"    
    ```