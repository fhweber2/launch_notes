###World's Collide!

basic rails app
-rails new
-bundle install

go to the gem file

for postgres add in the proper syntax

in the gemfile add - 'rspec-rails; 

open console (rails c)

    > Rails.env

    => "development"

    >Rails,env.development?
    
    => true


______

use 

    group :development, :test do
        gem 'rspec-rails'
    end
    
--------
    
initiate in the terminal

    rails g rspec:install
    
Rakefile 

    require 
    
    run rake
    

**In Sublime  use 'command + . ' to toggle b/w files   


####You always want your tests to express a story about the design of the program, db, etc.

Our models are where all of our Business Logic lies...as a Developer it is important to test these models.

    