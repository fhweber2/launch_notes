Admin Functionality 

Add a Feature

    admin_view_users_spec.rb
    
    describe 'viewing list of users ' do
    
        context 'as an Admin' do 
        
            it 'shows as list of all the users' do
                users = FactoryGirl.create_list
                visit new_user_session_path
                fill_in 'Email', with: admin.password
                click_button 'Sign in'
                
            end
            
            context 'as a user' do
                let (:user) {FactoryGirl.create(:user)}
                
                it 'does not show the list of users' do
                
                users = FactoryGirl.create.list(:user, 3)
                
                visits
                
    end
    
In the routes file

namespace :admin do 
    resources :users, only: [:index]
    
Now to Controllers

    admin
    
    users_controller
    
        class Admin::UsersController < ApplicationController
          
          before_filter :authorize_user 
          
            def index
                @users = Users.all
            end
            
            protected 
            
            def authorize_user
                unless 
In Views

    admin folder
    
        index.html.erb
        
            <h1> User</h1>
            <% @user.each do |user| %>
                <li><%= user.email %>
    
    
    
    class AdminController < ApplicationsController
        before_filter :authorize_user
        
        protected
        
        def authorize_user
            redirect_to root_path, notice: 'Unauthorized access' unless current_user.admin
        end
        
    
Look at CanCan Docs for functionality with the Admin Namespace