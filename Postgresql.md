Command Line:

    rails new postgres_example --database=postgresql
    
    subl .
    
Inside config folder (database.yml)

-test

-production

-development


**remove username/password data

    rake db:create  then rake db:migrate then rake db:seed
    
In your Gem File (line 8)

    gem 'pg'

    then bundle

________
    
####Switch Over 

Modify the database.yml file 

    adapter: postgresql
    
    database: 
    
Always want to match the local setup with your production environment 
