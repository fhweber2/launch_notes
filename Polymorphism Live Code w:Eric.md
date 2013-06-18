###Polymorphism

See the Guide:

http://guides.rubyonrails.org/association_basics.html#polymorphic-associations

####Setup ruby version and gemset for each program, etc.




    rails g devise:install

    rails g device:user

Simple Forms

In LikesController
    
    def create
        @racecar = Racecar.find(params[racecar_id])
        @likes =  @Racecar.likes.build
        @like.user = current.user
    
        if @like.save
            redirect_to racecare_path(@racecar)
        else
            render 
        end
        
    end
    
When testing if you have to log in to add a like or prop, etc.  Test login!

    FactoryGirl.define do
        factory user.
        
In the Support Folder

acquire the Authentication Helper for rspec

dependent: :destroy (can't have a like if you don't have an item - review, movie, etc.)





