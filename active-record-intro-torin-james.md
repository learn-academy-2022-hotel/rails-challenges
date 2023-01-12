rails new rolodex_challenge -d postgresql -T

cd rolodex_challenge
rails db:create
Created database 'rolodex_challenge_development'
Created database 'rolodex_challenge_test'

rails generate model Person first_name:string last_name:string phone:string
      invoke  active_record
      create    db/migrate/20230112192710_create_people.rb
      create    app/models/person.rb

rails db:migrate

rails 

Person.create first_name:'Torin', last_name:'Jacobs', phone:'888-123-4567'
Person.create first_name:'James', last_name:'Quillen', phone:'800-555-9999'
Person.create first_name:'Joe', last_name:'Schmoe', phone:'123-555-9999'
Person.create first_name:'Sally', last_name:'Hampton', phone:'456-555-9999'
Person.create first_name:'Fred', last_name:'Flinstone', phone:'789-555-9999'

Person.all

Person.where last_name:'Jacobs'

 Person.last.phone = '800-800-8000'

lens = Person.last
lens.phone = '800-800-8888'
lens.save

Person.third.first_name

Person.where(last_name:'Jacobs').update(phone:'888-123-4567')

Person.where.not(last_name:'Jacobs').destroy_all
