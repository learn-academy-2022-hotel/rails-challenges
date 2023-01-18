accountspec.rb

require 'rails_helper'

RSpec.describe Account, type: :model do
  it 'is valid with valid attributes' do
    matt = Account.create(username:'mlmunoz', password:'1234abcd', email:'matt@email.com')
    expect(matt).to be_valid
  end
  it 'is not valid without a username' do
    matt = Account.create(password:'1234abcd', email:'matt@email.com')
    expect(matt.errors[:username]).to_not be_empty
  end
  it 'is not valid without an email' do
    matt = Account.create(username:'mlmunoz', password:'1234abcd')
    expect(matt.errors[:email]).to_not be_empty
  end
  it 'is not valid without a password' do
    matt = Account.create(username:'mlmunoz', email:'matt@email.com')
    expect(matt.errors[:password]).to_not be_empty
  end
  it 'is not valid if username is less than 5 characters long' do
    matt = Account.create(username:'matt', password:'1234abcd', email:'matt@email.com')
    expect(matt.errors[:username]).to_not be_empty
  end
end

account.rb
class Account < ApplicationRecord
    validates :username, :email, :password, presence: true
    validates :username, length: { minimum: 6 }
end