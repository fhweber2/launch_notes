Dbs as Excel Columns 

Data are the rows


Rails 

Migrations = Structure

AR Instances = Data  or Records

Validations 


Structure (Schema) - write a Rails Migration

Models 

C

R

U

D

SQL: INSERT, SELECT, UPDATE, DELETE

AR: create/save, .all, .first, update_all/save, destroy

________


###Model 

always write a Migration first when you need to change the Schema.  Then you can run rake db:migrate

Create a Schema Change


    step 1.   rails g migration <name>  # an adjustment to the schema
   
    step 2.   implement migrate
   
    step 3.  rake db:migrate
   
    step 4.  rake db:rollback
   
    step 5.  rake db:migrate 
    
    step 6.  Check db/schema.rb
    
    step 7.  Check Code References
    
 ________
 
 Run a migration to drop users
 
    rails g migration drop_users
    
    class DropUsers
        def up
            drop_table :users
        end
        
        def down
            create table :users
        end
    end

___________

Schema v. Model Contraints

Recipes

Attributes (Author, Name, Ethnicity)

    rails g model recipe name:string author_first_name:sting, etc, etc.
    
Scheme Constraint
    
    null: false
    
rake db:migrate

rake db:rollback

rake db:migrate

then check the schema

model change - validates_presence_of in the model.


.persisted 

use .errors to check validations

Always mirror your schema constraints with the model

###Migration affects the Schema, Model the Data

    rake db:migrate && rails c

###Normalization

Normalize an author (affect a schema change)

    rails g model user first_name:string last_name:string
    
 Go update the table 
 
    add_column :recipes. :user_id
    
#### We only manipulate data (update), if we have to adhere to new schema constraints 


        Recipe.ind_each do |recipe|
            user = User.where ({ 
                first_name: recipe.author_first_name,
                last_name }).first 
                
            if user.nil?
            user = USer.create!({
            first_name: recipe.author_first,
            last_name: recipe.author_last_name 
            })
        end
        
        
the gist: 

    https://github.com/LaunchAcademy/recipes/blob/master/db/migrate/20130520211715_create_users.rb    


####Where the foreign key is is where the belongs_to (or belongs_to always belongs in the Model that has the foreign key, even if it doesn't make sense grammatically)   
   
    
Focus on the ER Diagram

Inverse (look to the Guides)

###has_many through

    class Owner
        has_many :appointments,
        through::pets,
        readonly : true 
    
    has_many :pets
    
    owner = Owner.first
    owner.appointments.create
    
    end