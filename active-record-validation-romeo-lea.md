Validations Challenges
Create a Rails application called company_contacts. The app will have a PostgreSQL database.

rails new validations -d postgresql -T

Generate a model called Account that has a username, a password, and an email.

rails g model Account username:string password:string email:string

All stories should have accompanying model specs.

rails g model Account username:string password:string email:string

Developer Stories

As a developer, I need username, password, and email to be required.

RSpec.describe Account, type: :model do
  it 'is not valid without a username, password, or email' do 
    romeo = Account.create
    expect(romeo.errors[:username,]).to_not be_empty
    expect(romeo.errors[:password,]).to_not be_empty
    expect(romeo.errors[:email,]).to_not be_empty
  end
end

class Account < ApplicationRecord
  validates :username, :password, :email, presence: true
end




As a developer, I need every username to be at least 5 characters long.
As a developer, I need each username to be unique.
As a developer, I need each password to be at least 6 characters long.
As a developer, I need each password to be unique.
As a developer, I want my Account model to have many associated Addresses.
As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.
As a developer, I want to validate the presence of all fields on Address.
Stretch Challenges

As a developer, I need each Account password to have at least one number.
HINT: Read about custom validations in the Active Record validation docs.
As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.
As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
HINT: Read about message in the validation docs.