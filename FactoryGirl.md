
    require 'factory_girl'

    
Create file in

    spec/support/factories.rb
    
_______
    
    FactoryGirl.define do
    # copy paste from spec_helper
    #
    #
    #
    end
    

    end

Then back in the spec_helper file 
to call a factory:

    FactoryGirl.build(:planet_destruction_event)
    end
    
    
Uniqueness

    sequence(:planet_name){|n| "Planet #{n}"}
    
    