<!-- Last login: Thu Jan 12 15:55:45 on ttys000
➜  bank_app git:(main) ✗ rails generate model Owner name:string address:string   
      invoke  active_record
      create    db/migrate/20230113184441_create_owners.rb
      create    app/models/owner.rb
➜  bank_app git:(main) ✗ rails db:migrate
== 20230113184441 CreateOwners: migrating =====================================
-- create_table(:owners)
   -> 0.0079s
== 20230113184441 CreateOwners: migrated (0.0079s) ============================

➜  bank_app git:(main) ✗ code .
➜  bank_app git:(main) ✗ rails generate model Card owner_id:interger exp_date:string number:interger 
Could not generate field 'owner_id' with unknown type 'interger'.
➜  bank_app git:(main) ✗ rails generate model Card owner_id:integer exp_date:string number:integer  
      invoke  active_record
      create    db/migrate/20230113185929_create_cards.rb
      create    app/models/card.rb
➜  bank_app git:(main) ✗ rails db:migrate
== 20230113185929 CreateCards: migrating ======================================
-- create_table(:cards)
   -> 0.0143s
== 20230113185929 CreateCards: migrated (0.0143s) =============================

➜  bank_app git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Owner.create(name: 'jeff', address: '456 swag st' )
  TRANSACTION (0.2ms)  BEGIN
  Owner Create (6.4ms)  INSERT INTO "owners" ("name", "address", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["name", "jeff"], ["address", "456 swag st"], ["created_at", "2023-01-13 19:10:54.713504"], ["updated_at", "2023-01-13 19:10:54.713504"]]                                                         
  TRANSACTION (5.0ms)  COMMIT                                                     
 =>                                                                               
#<Owner:0x00000001291e51e8                                                        
 id: 1,                                                                           
 name: "jeff",                                                                    
 address: "456 swag st",                                                          
 created_at: Fri, 13 Jan 2023 19:10:54.713504000 UTC +00:00,                      
 updated_at: Fri, 13 Jan 2023 19:10:54.713504000 UTC +00:00>                      
3.0.0 :002 > Owner.create(name: 'dave', address: '452 flame st' )
  TRANSACTION (0.2ms)  BEGIN
  Owner Create (0.4ms)  INSERT INTO "owners" ("name", "address", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["name", "dave"], ["address", "452 flame st"], ["created_at", "2023-01-13 19:11:34.681616"], ["updated_at", "2023-01-13 19:11:34.681616"]]                                                       
  TRANSACTION (0.5ms)  COMMIT                                                    
 =>                                                                              
#<Owner:0x000000013bd09a08                                                       
 id: 2,                                                                          
 name: "dave",                                                                   
 address: "452 flame st",                                                        
 created_at: Fri, 13 Jan 2023 19:11:34.681616000 UTC +00:00,                     
 updated_at: Fri, 13 Jan 2023 19:11:34.681616000 UTC +00:00>                     
3.0.0 :003 > Owner.create(name: 'mariah', address: '123 yolo st' )
  TRANSACTION (0.2ms)  BEGIN
  Owner Create (0.3ms)  INSERT INTO "owners" ("name", "address", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["name", "mariah"], ["address", "123 yolo st"], ["created_at", "2023-01-13 19:12:54.135583"], ["updated_at", "2023-01-13 19:12:54.135583"]]                                                      
  TRANSACTION (0.2ms)  COMMIT                                                    
 =>                                                                              
#<Owner:0x000000011c9d4758                                                       
 id: 3,                                                                          
 name: "mariah",                                                                 
 address: "123 yolo st",                                                         
 created_at: Fri, 13 Jan 2023 19:12:54.135583000 UTC +00:00,                     
 updated_at: Fri, 13 Jan 2023 19:12:54.135583000 UTC +00:00>                     
3.0.0 :004 > Owner.find(1).cards.create(exp_date:'02FEB1989', number:9876)
  Owner Load (0.3ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                  
  TRANSACTION (0.2ms)  BEGIN                                                      
  Card Create (5.3ms)  INSERT INTO "cards" ("owner_id", "exp_date", "number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["owner_id", 1], ["exp_date", "02FEB1989"], ["number", 9876], ["created_at", "2023-01-13 19:16:51.297939"], ["updated_at", "2023-01-13 19:16:51.297939"]]                        
  TRANSACTION (0.2ms)  COMMIT                                                     
 =>                                                                               
#<Card:0x000000011baf3108                                                         
 id: 1,                                                                           
 owner_id: 1,                                                                     
 exp_date: "02FEB1989",                                                           
 number: 9876,                                                                    
 created_at: Fri, 13 Jan 2023 19:16:51.297939000 UTC +00:00,                      
 updated_at: Fri, 13 Jan 2023 19:16:51.297939000 UTC +00:00> 
3.0.0 :005 >  Owner.find(2).cards.create(exp_date:'05FEB1999', number:6758)
  Owner Load (0.4ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
  TRANSACTION (0.1ms)  BEGIN
  Card Create (0.3ms)  INSERT INTO "cards" ("owner_id", "exp_date", "number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["owner_id", 2], ["exp_date", "05FEB1999"], ["number", 6758], ["created_at", "2023-01-13 19:18:11.870895"], ["updated_at", "2023-01-13 19:18:11.870895"]]
  TRANSACTION (0.3ms)  COMMIT
 => 
#<Card:0x000000013bd5e698
 id: 2,
 owner_id: 2,
 exp_date: "05FEB1999",
 number: 6758,
 created_at: Fri, 13 Jan 2023 19:18:11.870895000 UTC +00:00,
 updated_at: Fri, 13 Jan 2023 19:18:11.870895000 UTC +00:00> 
3.0.0 :006 >  Owner.find(3).cards.create(exp_date:'98FEB7865', number:8765)
  Owner Load (0.4ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 3], ["LIMIT", 1]]
  TRANSACTION (0.2ms)  BEGIN
  Card Create (0.3ms)  INSERT INTO "cards" ("owner_id", "exp_date", "number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["owner_id", 3], ["exp_date", "98FEB7865"], ["number", 8765], ["created_at", "2023-01-13 19:18:36.809800"], ["updated_at", "2023-01-13 19:18:36.809800"]]
  TRANSACTION (0.4ms)  COMMIT
 => 
#<Card:0x0000000119e60cc0
 id: 3,
 owner_id: 3,
 exp_date: "98FEB7865",
 number: 8765,
 created_at: Fri, 13 Jan 2023 19:18:36.809800000 UTC +00:00,
 updated_at: Fri, 13 Jan 2023 19:18:36.809800000 UTC +00:00> 
3.0.0 :007 > Card.all
  Card Load (0.5ms)  SELECT "cards".* FROM "cards"
 =>                                                         
[#<Card:0x000000011a1f1e70                                  
  id: 1,                                                    
  owner_id: 1,                                              
  exp_date: "02FEB1989",                                    
  number: 9876,                                             
  created_at: Fri, 13 Jan 2023 19:16:51.297939000 UTC +00:00,
  updated_at: Fri, 13 Jan 2023 19:16:51.297939000 UTC +00:00>,
 #<Card:0x000000011a1f1d58                                  
  id: 2,                                                    
  owner_id: 2,                                              
  exp_date: "05FEB1999",                                    
  number: 6758,                                             
  created_at: Fri, 13 Jan 2023 19:18:11.870895000 UTC +00:00,
  updated_at: Fri, 13 Jan 2023 19:18:11.870895000 UTC +00:00>,
 #<Card:0x000000011a1f1c90
  id: 3,
  owner_id: 3,
  exp_date: "98FEB7865",
  number: 8765,
  created_at: Fri, 13 Jan 2023 19:18:36.809800000 UTC +00:00,
  updated_at: Fri, 13 Jan 2023 19:18:36.809800000 UTC +00:00>] 
3.0.0 :008 > Owner.find(1).all
  Owner Load (0.4ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                  
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_methods.rb:458:in `method_missing': undefined method `all' for #<Owner id: 1, name: "jeff", address: "456 swag st", created_at: "2023-01-13 19:10:54.713504000 +0000", updated_at: "2023-01-13 19:10:54.713504000 +0000"> (NoMethodError)    
3.0.0 :009 > Owner.all
  Owner Load (0.4ms)  SELECT "owners".* FROM "owners"
 =>                                                                               
[#<Owner:0x000000012a064160                                                       
  id: 1,                                                                          
  name: "jeff",                                                                   
  address: "456 swag st",                                                         
  created_at: Fri, 13 Jan 2023 19:10:54.713504000 UTC +00:00,                     
  updated_at: Fri, 13 Jan 2023 19:10:54.713504000 UTC +00:00>,                    
 #<Owner:0x000000013bfe3fd0                                    
  id: 2,                                                       
  name: "dave",                                                
  address: "452 flame st",                                     
  created_at: Fri, 13 Jan 2023 19:11:34.681616000 UTC +00:00,  
  updated_at: Fri, 13 Jan 2023 19:11:34.681616000 UTC +00:00>, 
 #<Owner:0x000000013bfe3e40                                    
  id: 3,
  name: "mariah",
  address: "123 yolo st",
  created_at: Fri, 13 Jan 2023 19:12:54.135583000 UTC +00:00,
  updated_at: Fri, 13 Jan 2023 19:12:54.135583000 UTC +00:00>] 
3.0.0 :010 > Owner.Card.all
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `Card' for Owner:Class (NoMethodError)                                                               
3.0.0 :011 > Owner.cards
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activerecord-7.0.4/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `cards' for Owner:Class (NoMethodError)                                                              
3.0.0 :012 > Owner.find(1).cards
  Owner Load (0.4ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                  
  Card Load (0.2ms)  SELECT "cards".* FROM "cards" WHERE "cards"."owner_id" = $1  [["owner_id", 1]]                                                                 
 =>                                                                               
[#<Card:0x000000011a132638                                                        
  id: 1,                                                                          
  owner_id: 1,                                                                    
  exp_date: "02FEB1989",                                                          
  number: 9876,                                                                   
  created_at: Fri, 13 Jan 2023 19:16:51.297939000 UTC +00:00,                     
  updated_at: Fri, 13 Jan 2023 19:16:51.297939000 UTC +00:00>]                    
3.0.0 :013 > Owner.find(1).cards.create(exp_date:'03FEB8976', number:7291)
  Owner Load (0.5ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                  
  TRANSACTION (0.1ms)  BEGIN                                                      
  Card Create (0.3ms)  INSERT INTO "cards" ("owner_id", "exp_date", "number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["owner_id", 1], ["exp_date", "03FEB8976"], ["number", 7291], ["created_at", "2023-01-13 19:22:58.071954"], ["updated_at", "2023-01-13 19:22:58.071954"]]                        
  TRANSACTION (0.2ms)  COMMIT                                                     
 =>                                                                               
#<Card:0x000000011c815188                                                         
 id: 4,                                                                           
 owner_id: 1,                                                                     
 exp_date: "03FEB8976",                                                           
 number: 7291,                                                                    
 created_at: Fri, 13 Jan 2023 19:22:58.071954000 UTC +00:00,                      
 updated_at: Fri, 13 Jan 2023 19:22:58.071954000 UTC +00:00> 
3.0.0 :014 > Owner.find(1).cards.create(exp_date:'08FEB2002', number:9873)
  Owner Load (0.3ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]
  TRANSACTION (0.1ms)  BEGIN
  Card Create (0.4ms)  INSERT INTO "cards" ("owner_id", "exp_date", "number", "created_at", "updated_at") VALUES ($1, $2, $3, $4, $5) RETURNING "id"  [["owner_id", 1], ["exp_date", "08FEB2002"], ["number", 9873], ["created_at", "2023-01-13 19:23:33.925407"], ["updated_at", "2023-01-13 19:23:33.925407"]]
  TRANSACTION (0.4ms)  COMMIT
 => 
#<Card:0x0000000119b32a08
 id: 5,
 owner_id: 1,
 exp_date: "08FEB2002",
 number: 9873,
 created_at: Fri, 13 Jan 2023 19:23:33.925407000 UTC +00:00,
 updated_at: Fri, 13 Jan 2023 19:23:33.925407000 UTC +00:00> 
3.0.0 :015 > Owner.find(1).cards
  Owner Load (0.4ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                  
  Card Load (0.3ms)  SELECT "cards".* FROM "cards" WHERE "cards"."owner_id" = $1  [["owner_id", 1]]                                                                 
 =>                                                                               
[#<Card:0x000000011a04df60                                                        
  id: 1,                                                                          
  owner_id: 1,                                                                    
  exp_date: "02FEB1989",                                                          
  number: 9876,                                                                   
  created_at: Fri, 13 Jan 2023 19:16:51.297939000 UTC +00:00,                     
  updated_at: Fri, 13 Jan 2023 19:16:51.297939000 UTC +00:00>,                    
 #<Card:0x000000011a04dc40                                                        
  id: 4,                                                                          
  owner_id: 1,                                                                    
  exp_date: "03FEB8976",
  number: 7291,
  created_at: Fri, 13 Jan 2023 19:22:58.071954000 UTC +00:00,
  updated_at: Fri, 13 Jan 2023 19:22:58.071954000 UTC +00:00>,
 #<Card:0x000000011a04d920
  id: 5,
  owner_id: 1,
  exp_date: "08FEB2002",
  number: 9873,
  created_at: Fri, 13 Jan 2023 19:23:33.925407000 UTC +00:00,
  updated_at: Fri, 13 Jan 2023 19:23:33.925407000 UTC +00:00>] 
3.0.0 :016 > exit
➜  bank_app git:(main) ✗ rails generate model Limit credit_limit:integer card_id:integer
      invoke  active_record
      create    db/migrate/20230113192721_create_limits.rb
      create    app/models/limit.rb
➜  bank_app git:(main) ✗ rails db:migrate
== 20230113192721 CreateLimits: migrating =====================================
-- create_table(:limits)
   -> 0.0133s
== 20230113192721 CreateLimits: migrated (0.0133s) ============================

➜  bank_app git:(main) ✗ rails c
Loading development environment (Rails 7.0.4)
3.0.0 :001 > Limit.all
  Limit Load (0.7ms)  SELECT "limits".* FROM "limits"
 => []                                                                      
3.0.0 :002 > Card.find(1).limits.create(credit_card_limit:integer) 
  Card Load (0.4ms)  SELECT "cards".* FROM "cards" WHERE "cards"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                      
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_methods.rb:458:in `method_missing': undefined method `limits' for #<Card id: 1, owner_id: 1, exp_date: "02FEB1989", number: 9876, created_at: "2023-01-13 19:16:51.297939000 +0000", updated_at: "2023-01-13 19:16:51.297939000 +0000"> (NoMethodError)                                                                        
Did you mean?  limit                                                              
               limit=                                                             
3.0.0 :003 > Card.find(1).limit.create(credit_card_limit:integer) 
  Card Load (0.8ms)  SELECT "cards".* FROM "cards" WHERE "cards"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                      
  Limit Load (0.2ms)  SELECT "limits".* FROM "limits" WHERE "limits"."card_id" = $1 LIMIT $2  [["card_id", 1], ["LIMIT", 1]]                                        
(irb):3:in `<main>': undefined local variable or method `integer' for main:Object (NameError)
Did you mean?  Integer
3.0.0 :004 > Card.find(1).limit.create(credit_limit:integer) 
  Card Load (0.4ms)  SELECT "cards".* FROM "cards" WHERE "cards"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                      
  Limit Load (0.2ms)  SELECT "limits".* FROM "limits" WHERE "limits"."card_id" = $1 LIMIT $2  [["card_id", 1], ["LIMIT", 1]]                                        
(irb):4:in `<main>': undefined local variable or method `integer' for main:Object (NameError)                                                                       
Did you mean?  Integer                                                            
3.0.0 :005 > Card.find(1).limit.create(credit_limit:123456789) 
  Card Load (0.4ms)  SELECT "cards".* FROM "cards" WHERE "cards"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                      
  Limit Load (0.2ms)  SELECT "limits".* FROM "limits" WHERE "limits"."card_id" = $1 LIMIT $2  [["card_id", 1], ["LIMIT", 1]]                                        
(irb):5:in `<main>': undefined method `create' for nil:NilClass (NoMethodError)   
3.0.0 :006 > Card.find(1).limits.create(credit_limit:123456789) 
  Card Load (0.4ms)  SELECT "cards".* FROM "cards" WHERE "cards"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_methods.rb:458:in `method_missing': undefined method `limits' for #<Card id: 1, owner_id: 1, exp_date: "02FEB1989", number: 9876, created_at: "2023-01-13 19:16:51.297939000 +0000", updated_at: "2023-01-13 19:16:51.297939000 +0000"> (NoMethodError)
Did you mean?  limit
               limit=
3.0.0 :007 > Card.find(1).Limit.create(credit_limit:123456789) 
  Card Load (0.5ms)  SELECT "cards".* FROM "cards" WHERE "cards"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                      
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_methods.rb:458:in `method_missing': undefined method `Limit' for #<Card id: 1, owner_id: 1, exp_date: "02FEB1989", number: 9876, created_at: "2023-01-13 19:16:51.297939000 +0000", updated_at: "2023-01-13 19:16:51.297939000 +0000"> (NoMethodError)                                                                         
Did you mean?  limit=                                                             
3.0.0 :008 > Card.find(1).limits.create(credit_limit:123456789) 
  Card Load (0.3ms)  SELECT "cards".* FROM "cards" WHERE "cards"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                      
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_methods.rb:458:in `method_missing': undefined method `limits' for #<Card id: 1, owner_id: 1, exp_date: "02FEB1989", number: 9876, created_at: "2023-01-13 19:16:51.297939000 +0000", updated_at: "2023-01-13 19:16:51.297939000 +0000"> (NoMethodError)                                                                        
Did you mean?  limit                                                              
               limit=                                                             
3.0.0 :009 > Card.find(1).limits.create(credit_limit:123456789) 
  Card Load (0.4ms)  SELECT "cards".* FROM "cards" WHERE "cards"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                      
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_methods.rb:458:in `method_missing': undefined method `limits' for #<Card id: 1, owner_id: 1, exp_date: "02FEB1989", number: 9876, created_at: "2023-01-13 19:16:51.297939000 +0000", updated_at: "2023-01-13 19:16:51.297939000 +0000"> (NoMethodError)
Did you mean?  limit
               limit=
3.0.0 :010 > Owner.find(1).Card.find(1).limit.create(credit_limit:123456789) 
  Owner Load (0.5ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                  
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/activemodel-7.0.4/lib/active_model/attribute_methods.rb:458:in `method_missing': undefined method `Card' for #<Owner id: 1, name: "jeff", address: "456 swag st", created_at: "2023-01-13 19:10:54.713504000 +0000", updated_at: "2023-01-13 19:10:54.713504000 +0000"> (NoMethodError)   
Did you mean?  cards                                                              
3.0.0 :011 > Owner.find(1).cards.find(1).limit.create(credit_limit:123456789) 
  Owner Load (0.4ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                  
  Card Load (0.3ms)  SELECT "cards".* FROM "cards" WHERE "cards"."owner_id" = $1 AND "cards"."id" = $2 LIMIT $3  [["owner_id", 1], ["id", 1], ["LIMIT", 1]]         
  Limit Load (0.1ms)  SELECT "limits".* FROM "limits" WHERE "limits"."card_id" = $1 LIMIT $2  [["card_id", 1], ["LIMIT", 1]]                                        
(irb):11:in `<main>': undefined method `create' for nil:NilClass (NoMethodError)  
3.0.0 :012 > Owner.find(1).cards.find(1).limit.create(credit_limit:123456789) 
  Owner Load (1.0ms)  SELECT "owners".* FROM "owners" WHERE "owners"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]                                                  
  Card Load (0.6ms)  SELECT "cards".* FROM "cards" WHERE "cards"."owner_id" = $1 AND "cards"."id" = $2 LIMIT $3  [["owner_id", 1], ["id", 1], ["LIMIT", 1]]         
  Limit Load (0.4ms)  SELECT "limits".* FROM "limits" WHERE "limits"."card_id" = $1 LIMIT $2  [["card_id", 1], ["LIMIT", 1]]                                        
(irb):12:in `<main>': undefined method `create' for nil:NilClass (NoMethodError)  
3.0.0 :013 >  -->