<!-- Create three owners and save them in the database
Owner.create(name:'James', address:'333 Five St')
Owner.create(name:'Oscar', address:'555 Five St')
Owner.create(name:'Trish', address:'888 Five St')

Create a credit card in the database for each owner
CreditCard.create(number:2345,expiration_date:20240115,owner_id:2)
CreditCard.create(number:1234,expiration_date:20240115,owner_id:1)
CreditCard.create(number:3456,expiration_date:20240115,owner_id:3)

Add two more credit cards to one of the owners
oscar.credit_cards.create(number:2342,expiration_date:20250116)
oscar.credit_cards.create(number:2341,expiration_date:20250116)

Stretch Challenge
Add a credit limit to each card

CreditCard.all.update(credit_limit:15000)

Find the total credit extended to the owner with multiple credit cards
-CreditCard.where(owner_id:1).sum(:credit_limit)

 -->