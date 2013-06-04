Database - a system of tables 
    
Tables - schema + data

Schema - Table Structure

Data - info in the schema

example:  news articles and comments

-----

In Rails 

-migrations
 
-ActiveRecord

---

Migration mistakes / new thoughts 

Differences between migration file & model file

attr_accesible v. attr_accessor

default values

datatypes

____

rails generate model (is generating code for us)

rake db: migrate

(CMD + t) function in rails

    1rake db:rollback

schema.rb file in the rails app to check your schema

rails generate migration (make_name_not_null)

timestamps (deep dive) on UTC


    change_col :pets, :name, :string, 
    
attribute can never be 

_____

###Rails is just Ruby Code

_____

To roll-back 

    null: false  or  null: true
    
________

    rake db:migrate db: rollback
    

###Migrations 

change  create an up/down

Versioning your Schema

__________

###Model 

    attr_accessible:  name

A security function in Rails

To get into the Rails Console type:

    rails c
    
    
A virtual attribute (not persistent / stored in the database or schema)



schema                -migration               -DDL

records/data        -model                   - SQL


###C  -  create  (insert)


###R  - retrieve (select)


###U  - update  (update)


###D - delete  (delete)

_______

Up, Down and Change in the Migration Object


    class AddAnimalType < ActiveRecord::Migration
        def up
            add_column :pets, :animal_type, :string
        
        Pet.update_all("animal_type = 'dog'")
        
        change_column :pets, :animal_type, :string, : 
        
        end
        
        def down
            remove_column :pets, animal_type, :string
        end
     end       

###Ruby 'nil' is == to SQL 'nil'

-Note to self - check to see if the attr_accessor is being utilized in the Migration record when trying to change values, name types, etc.

________

###Datatypes

-String

-Integers

-Text

-DateTime


