$ rails new bank_app -d postgresql -T
$ cd bank_app
$ rails db:create
$ rails generate model CreditCard number:integer expiration_date:date owner:integer
$ rails db:migrate
$ rails generate model Owner name:string address:string
$ rails db:migrate
# Add belongs_to :owner to credit_card.rb and 
# has_many :credit_cards to owner.rb
$ rails server
# By convention the foreign key should always be the modelname_id and the data type should be integer. We created a new migration file to modify the owner column name in the CreditCards table to owner_id. using the following command:
$ rails generate migration change_owner_column_name
      invoke  active_record
      create    db/migrate/20230114194609_change_owner_column_name.rb
# Make the following modification to the change method in the new activer record file created:
    rename_column(:credit_cards, :owner, :owner_id)
$ rails db:migrate
== 20230114194609 ChangeOwnerColumnName: migrating ============================
-- rename_column(:credit_cards, :owner, :owner_id)
   -> 0.0117s
== 20230114194609 ChangeOwnerColumnName: migrated (0.0117s) ===================

$ rails c
3.0.0 :005 > fred = Owner.first
3.0.0 :009 > fred.credit_cards.create number:123456, expiration_date:"2025-01-31"

$ rails generate migration add_credit_limit_to_credit_cards credit_limit:integer
# Check that new migration file was created
$ rails db:migrate
# Check that schema.rb file was updated with the new column
# might need to restart the console for changes to show
3.0.0 :043 octavio.credit_cards.create number:678901, expiration_date:"2027-01-31", credit_limit:1000
# Update the credit limit 
3.0.0 :043 CreditCard.find(2).update(credit_limit:500)
# Find the total credit limit for an owner
3.0.0 :043 o_total = 0
3.0.0 :043 o = CreditCard.where(owner_id:2)
3.0.0 :043 > o.each
    => #<Enumerator: ...> 
3.0.0 :048 > o_total = 0
3.0.0 :050 > o.each do |e| o_total+=e.credit_limit end
3.0.0 :051 > o_total
 => 4400 
 # You can write methods in console
 3.0.0 :067 > def total_credit(customer)
3.0.0 :068 >   total_credit_extended = 0 
3.0.0 :069 >   customer.each do |credit_card| 
3.0.0 :070 >     total_credit_extended+=credit_card.credit_limit
3.0.0 :071 >   end
3.0.0 :072 >   total_credit_extended
3.0.0 :073 > end
 => :total_credit 
 3.0.0 :077 > total_credit(CreditCard.where(owner_id:1))
  CreditCard Load (0.7ms)  SELECT "credit_cards".* FROM "credit_cards" WHERE "credit_cards"."owner_id" = $1  [["owner_id", "1"]]
 => 500  
 3.0.0 :075 > octavio_ccs = CreditCard.where(owner_id:2)
 3.0.0 :076 > total_credit(octavio_ccs)
 => 4400 