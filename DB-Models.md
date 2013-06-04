##Recap

_______

####Db's

Schema   "structure"            

 data    "information"
 
 SQL     "language"
 
 Constraints
 
______
 
####ActiveRecord

Migration

Models

Ruby

Validation 

_________________

####Operations

C
R
U
D


_________

####SQL
*(all Upcase)

INSERT

SELECT

UPDATE

DELETE

_________

AR

Create/Save

finds/AREL

Update_all, save, update_attribute

destroy

___________

###In the rails console

to reload the console 

    reload!
  

Schema Constraints must equal your Database Contraints

Always be as defensive as possible when getting input from your users

Migrations to affect changes on our schema

Rename:

2-steps rename the table
then change the name of the class (change the model to do this)


    rails g migration rename pet_table 
    
rename_table is a method in ActiveRecord for the def up

 for the down method use the inverse e.g if up is :animals, :pets then in the down method use :pets, :animals
 
    def up 
        rename_table :pets, :animals
    end
    
    def down
        rename_table :animals, :pets
    end
__________


mv app (need the command for this )


Validations         --> Your App/Code

Constraints            --> Database

db/schema.rb


Rails Dependencies 
    
    
ActiveRecord  - CRUD (input, update, etc.) Bridge b/w : Model

ActiveModel - assist in validation 

ActionPack - Controller / View

ActiveSupport - The "Glue"






