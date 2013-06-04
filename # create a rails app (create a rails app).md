# create a rails app

  1. rails new<app_name>  --database=postgresql

  2. remove public/index

  3. edit config/database.yml host: 127.0.0.1

  4. gem file updates

# gemfile

    
    group :test, :development do
        gem 'rspec-rails'
        gem 'capybara'
        gem 'launchy'
    end
    
    group :test do
        gem 'factory_girl_rails'
    end
    

  5. bundle

  6. rails g rspec:install

  7. remove test/

  8. add to spec_helper.rb

# spec_helper.rb

    
    require 'capybara/rspec'
    
    config.include FactoryGirl::Syntax::Methods
    
  9. git commit

  10. rake db:create

  11. create models / scaffold / migrations

  12. git commit

  13. rake db:migrate ; rake db:rollback ; rake db:migrate

  14. git commit

