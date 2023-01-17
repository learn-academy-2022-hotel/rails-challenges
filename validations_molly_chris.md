Validations Challenges

Create a Rails application called company_contacts. The app will have a PostgreSQL database.



Generate a model called Account that has a username, a password, and an email.

rails g model Account username:string password:string email:string

All stories should have accompanying model specs.
Developer Stories

As a developer, I need username, password, and email to be required.



As a developer, I need every username to be at least 5 characters long.
As a developer, I need each username to be unique.
As a developer, I need each password to be at least 6 characters long.
As a developer, I need each password to be unique.
As a developer, I want my Account model to have many associated Addresses.
As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.
As a developer, I want to validate the presence of all fields on Address.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
in account_spec.rb:
RSpec.describe Account, type: :model do
  it 'is valid with valid attributes' do
    chris_acc = Account.create(username:'chris', password:'password', email:'chris@email.com')
    expect(chris_acc).to be_valid
  end
  it 'is not valid if username is shorter than 5 characters' do
    chris_acc = Account.create(username:'c', password:'password', email:'chris@email.com')
    expect(chris_acc.errors[:username]).to_not be_empty
  end
  it 'is not valid if username is not unique' do
    chris_acc = Account.create(username:'testing', password:'password', email:'chris@email.com')
    molly_acc = Account.create(username:'testing', password:'passwords', email:'molly@email.com')
    expect(molly_acc.errors[:username]).to_not be_empty
  end
  it 'is not valid if password is less than 6 characters' do
    chris_acc = Account.create(username:'chrisss', password:'pw', email:'chris@email.com')
    expect(chris_acc.errors[:password]).to_not be_empty
  end
  it 'is not valid if password is not unique' do
    chris_acc = Account.create(username:'chris', password:'password', email:'chris@email.com')
    molly_acc = Account.create(username:'molly', password:'password', email:'molly@email.com')
    expect(molly_acc.errors[:password]).to_not be_empty
  end
end

in account.rb
class Account < ApplicationRecord
    validates :username, length: { minimum: 5 }, uniqueness: true
    validates :password, length: { minimum: 6 }, uniqueness: true
    has_many :addresses
end

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

Stretch Challenges

As a developer, I need each Account password to have at least one number.
HINT: Read about custom validations in the Active Record validation docs.
As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.
As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
HINT: Read about message in the validation docs.