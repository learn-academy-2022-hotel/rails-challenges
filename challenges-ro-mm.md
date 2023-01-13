Challenges
Create three owners and save them in the database
> rails c
>Owner.create(name:'Raymond', address:'123 anywhere st.')
>Owner.create(name:'Matt', address: '1021 Somewhere Ave')
>Owner.create(name:'Jeremy', address:'2100 House St.')
Create a credit card in the database for each owner
> raymond.credit_cards.create(number:'0000 1111', expiration_date:'01
/23/2023')
>matt.credit_cards,create(number:'1111 2222', expiration_date:'02/01
/23')
>jeremy.credit_cards.create(number: '7777 9999', expiration_date:'03/02/24')

Add two more credit cards to one of the owners
>jeremy.credit_cards.create(number: '0546 3245', expiration_date:'09/22/24')
>jeremy.credit_cards.create(number:'4444 5555', expiration_date:'05/04/23')

Stretch Challenge
Add a credit limit to each card
>card_one = CreditCard.find(1)
card_one.update(credit_limit: 1000)

>card_two = CreditCard.find(2)
card_two.update(credit_limit: 2000)

>card_three = CreditCard.find(3)
card_three.update(credit_limit: 3000)

>card_four = CreditCard.find(4)
card_four.update(credit_limit: 4000)

>card_five = CreditCard.find(5)
card_five.update(credit_limit: 50000)

Find the total credit extended to the owner with multiple credit cards
>jeremy.credit_cards.sum(:credit_limit)
