# Setup
- Create a new rails application and database
    ```
    rails new banking_challenge -d postgresql -T
    rails db:create
    ```

- Create a model for owner
- An owner has a name and address, and can have multiple credit cards
    ```
    rails generate model Owner name:string address:string credit_card:string
    ```


- Create a model for credit card
- A credit card has a number, an expiration date, and an owner
    ```
    rails generate model CreditCard number:string expiration_date:date owner_id:integer
    ```

# Challenges
- Create three owners and save them in the database
    ```
    Owner.create(name:'Bora Ros', address:'1234 Random St', credit_card:'yes')
    Owner.create(name:'Molly Wolf', address:'567 Other St', credit_card:'yes')
    Owner.create(name:'Matt Munoz', address:'1212 New Rd', credit_card:'yes')
    ```

- Create a credit card in the database for each owner
    ```
    bora_card.credit_cards.create(number:'123456789', expiration_date:'2025-13-03')
    molly_card.credit_cards.create(number:'12121212', expiration_date:'2027-23-11')
    matt_card.credit_cards.create(number:'555555555', expiration_date:'2024-16-01')
    ```

- Add two more credit cards to one of the owners
    ```
    matt_card.credit_cards.create(number:'987654321', expiration_date:'2027-26-12')
    matt_card.credit_cards.create(number:'21212121', expiration_date:'2023-02-12')
    ```

# Stretch Challenge
- Add a credit limit to each card
    ```
    rails generate migration add_columns_to_creditcard
    rails db:migrate
    CreditCard.find(1).update(credit_limit:1500)
    ```

- Find the total credit extended to the owner with multiple credit cards
    ```
    CreditCard.where(owner_id:3).sum(:credit_limit)
    ```