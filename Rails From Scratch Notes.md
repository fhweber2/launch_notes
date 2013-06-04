Nested Resources

    route.rb

    resources :trips 
    
In the model 
        
        attr_accessible :description, :name
        
        belongs_to :trip
    end

add an _id 

    In the Applications.routes.draw do
        resources :destinations
        
        resources :trips do
            resources :destinations  # nested in trips to better map
        end
        
        root to: 'trips#index'
    
    rake routes
    
    In show.html.erb
        
        <%= link_to 'New Destination', new_trip_destination_path(@trip) %>

Add classes for tables via bootstrap

Goto the Controller

    def new
        @trip = Trip.find(params[:trip_id]) # then goto for 
        @destination = @trip.destinations.new(params[:destination])

To the create method

     def create 
        @trip = Trip.find(params[:trip_id])
        @destination = Destination.new(params[:destination])

Back to def edit
    
        
    

Model 

    trip 
    
     