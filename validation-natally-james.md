# account.rb

```
class Account < ApplicationRecord
    has_many :addresses
    validates :username, :password, :email, presence: true
    validates :username, length: { minimum: 5 }
    validates :username, uniqueness: true
    validates :password, length: { minimum: 6 }
    validates :password, uniqueness: true
end
```

# account_spec.rb

```
require 'rails_helper'

RSpec.describe Account, type: :model do
  it 'has to have a username, password, and email' do
    bob = Account.create
    expect(bob.errors[:username]).to_not be_empty
    expect(bob.errors[:password]).to_not be_empty
    expect(bob.errors[:email]).to_not be_empty
  end

  it 'requires usernames to be at least 5 characters long' do
    bob = Account.create username: "Bob"
    expect(bob.errors[:username]).to_not be_empty
  end

  it 'requires a unique username' do
    bob = Account.create username: "Bob"
    bob2 = Account.create username: "Bob"
    expect(bob.errors[:username]).to_not be_empty
  end 

  it 'requires passwords to be at least 6 characters long' do
    bob = Account.create password: "shh"
    expect(bob.errors[:password]).to_not be_empty
  end

  it 'requires unique passwords' do
    bob = Account.create password: "Bob"
    bob2 = Account.create password: "Bob"
    expect(bob.errors[:password]).to_not be_empty
  end

end
```

# address.rb

```
class Address < ApplicationRecord
    belongs_to :account
    validates :street_number, :street_name, :city, :state, :zip, presence: true
end
```

# address_spec.rb

```
require 'rails_helper'

RSpec.describe Address, type: :model do
  it 'has to have all fields filled out' do
    place = Address.create
    expect(place.errors[:street_number]).to_not be_empty
    expect(place.errors[:street_name]).to_not be_empty
    expect(place.errors[:city]).to_not be_empty
    expect(place.errors[:state]).to_not be_empty
    expect(place.errors[:zip]).to_not be_empty
  end
end
```