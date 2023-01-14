$ rails new bank_app -d postgresql -T
$ cd bank_app
$ rails db:create
$ rails generate model CreditCard number:integer expiration_date:date owner:integer
$ rails db:migrate
$ rails generate model Owner name:string address:string
$ rails db:migrate
$ rails server

# By convention the foreign key should always be the modelname_id and the data type should be integer. 

$ rails generate migration change_owner_column_name
      invoke  active_record
      create    db/migrate/20230114194609_change_owner_column_name.rb

# Make the following modification to the change method in the new activer record file created:
    - rename_column(:credit_cards, :owner, :owner_id)
    
$ rails db:migrate
== 20230114194609 ChangeOwnerColumnName: migrating ============================
-- rename_column(:credit_cards, :owner, :owner_id)
   -> 0.0117s
== 20230114194609 ChangeOwnerColumnName: migrated (0.0117s) ===================


