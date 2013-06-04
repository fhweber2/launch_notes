Remove the request spec

rm rf spec/request


always 

    require 'spec_helper'
    
    describe 'creating a planet destruction event' do
        # As a grand moff of mass destruction
        # I want to record planet destruction events
        # So that I can demonstrate imperial awesomeness
        
        # Acceptance Criteria
        # * I must specify a planet name, star system, casualty count,
        # and description
        #* I get a confirmation that my planet destruction event was recorded
        
        it 'creates a valid event when all required attribute are specified' do
            prev_count '/planet_destruction_events/new'
            
            # I navigate to the new planet destruction event form
            visit '/planet_destruction_events/new'
             # I fill in the required fields
           
            fill_in "Planet name", with 'Alderon'
            fill_in "Star system", with 'Alderon'
            fill_in "Casualties", with '30000000'
            fill_in "Description", with 'Oops! My bad!'
           
            # I submit the form
            
            click_button 'Create planet destruction event'
            
            # I verify that the destruction event was recorded 
        end
        
        expect(PlanetDestructionEvenr.count).to eql(prev_count +1)
        
        end
        
        it 'does not create an event when I miss a required attribute'
        it 'confirms that I have created a valid event'
        
    end
        it 'does not create an event when I miss a required attribute' do
            visit '/planet_destruction_events/new'
            
            click_button 'Create Planet destruction even'
            
            expect(PlanetDestruction.count).to eql
            
            
   
   
   
    rake db:migrate && rake spec
    
    within blocks for multiple buttons with the same name
    
    What is the expected outcome of the test - a critical part of the mental aspects of TDD
    
    
        describe PlanetDestructionEvent do
            
            it 'validates that I specify a planet name' do
            PlanetDestructionEvent.new do | event |
                event.planet_name = nil
                event.star_system = 'Alderon'
                event.casualties = 100
                event.description = 'Derp, wrong planet'
            end
            
                expect(event) .to_not be_valid
            it 'validates that I specify a star system'
            it 'validates that I specify a casualty count'
            it 'validates that I specify a description'
        end
    
        expect(PlanetDestructionEvent.count).to sql(prev_count)
        expect(page).to have_content('can't be blank')
    end
    
    # in the model validate 
        
            validates_presence_of :planet_name
            
    #rules are:
        null constraints for presence
        unique indexes for unique indexes 
        
  Red Green Refactor
  
    remember to use a 'let' and a .dup   
    
Outside in Philosophy of Development (A Test Driven Developer)

You don't know what you don't know (as a agile, test driven dev)  we don't write pseudocode without a user story
 
###Models are just ruby objects
Treat your models like your average, plain old ruby object (PORO). In this assignment, you learned that you can define class and instance methods on an ActiveRecord class like you can with any other ruby object.
   