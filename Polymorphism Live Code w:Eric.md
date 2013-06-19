###Polymorphism

See the Guide:

http://guides.rubyonrails.org/association_basics.html#polymorphic-associations

####Setup ruby version and gemset for each program, etc.




    rails g devise:install

    rails g device:user

Simple Forms


    class LikesController < ApplicationController
    
        def create
            @racecar = Racecar.find(params[racecar_id])
            @likes =  @Racecar.likes.build
            @like.user = current.user
        
         if @like.save
            redirect_to racecare_path(@racecar)
         else
            render (or redirect_to :back)
        end
       end 
    end
    
When testing if you have to log in to add a like or prop, etc.  Test login!

    FactoryGirl.define do
        factory user.
        
In the Support Folder

acquire the Authentication Helper for rspec

    dependent: :destroy # can't have a like if you don't have an item - review, movie, etc.


####Remember to scope the Routes 

    only: [:xxxx]
___    
    
    <ul> 

        <li><%=  @racecar.name  %> </li>
        <li><%=  @racecar.top_speed  %></li>
        <li><%=  @racecar.color   %></li>
        <li><%=  @racecar.crash_test_rating %></li>
    </ul
    
        <%= simple_form_for [@racecar, @likes] %>
        <%=  form submit    %>

_________

    private
    def parent      # can use 'parent' instead of hard coding in "beer" "racecar" etc
        @parent ||= find_parent
    end
    
    def find_parent
        parent = nil
        
    params.each do |key. value|
        if key =~ /(.+)_id$/
            parent = $1.classify.constantize.find(value)
        end
    end
    
___________
    
    belongs_to: likeable 
    
    has_many: likeables,
                     :as 
                    
____________

rails g migration 

    add_column :likes, :likeable_id, :integer
    add_column :likes, :likeable_id, :string
    
    remove_column :likes,  likeable_id
    remove_column :likes, :likeable_id