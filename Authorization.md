###Authorization

-Administrative functions  v. User Functions

-The Evaluation Process of using particular Gems (open-source ecosystem)

####CanCan (lots of info on the wiki), plus an older RailsCast - circa 2009 w/Rails 2.x

add to Gemfile, then
    
    bundle
    
    rails g cancan:something

Some live code: 

In spec file (adding a new task)

    require 'spec_helper'
    
        describe "adding a new task" do
        
        context "when an admin" do
                
         let(:admin) { FactoryGirl.create(:admin) }

          it "shows a link for creating a task on the index page" do
            
            visit root_path
                
            fill_in "Email", with: admin.email
            fill_in "Password". with admin.email
            
            click_button "Sign in"
            
            page.should have_link("New Task,", new_task_path)

        end
    end
   

       context "when a non-admin" do
        let(:user) { FactoryGirl.create(:user)}

        it "does not "
        
                 
        FactoryGirl.define do
         factory :user do
            email "foo@example.com"
            password "12345678"
            role "user"
            
            factory :admin do
                role "admin"
          end
        end
       end
                            
                            
Create a user_spec for the migration (creating a validation - check out the guide)

###Valid Attribute (shoulda) - a more expressive assertion to test validations 

    gem "shoulda-matchers"  

    require "spec_helper"
    
        describe User do
            it {  should ensure_inclusion_of(:role).in_an_array( ["user" , "admin"] ) }
            
        describe "#is_admin?" do
            it "checks the role for admin privileges"
                        
        
        end
                
    
in the CanCan (class)

    class Ability 
        include CanCan::Ability 
            
        def initialize(user)
            
            if user.admin?
                can :manage, :all
            else
                can :read, :all
            end
          end
        end
    

Test, Create roles, validates in the model, test, 

Controller test

from the command line using cURL test all of the routes.


Look at Changing Defaults in the wiki


