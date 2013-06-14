
###Carrierwave

note: carrierwave docs  - 
Content - Type

html/text

text/csv

application/xls

multipart message 

jQuery File Upload


Live Code:

for an acceptance test uses 'feature' (features tests)

    feature 

Hit start on Pivotal Tracker add a 'feature' test 

    require 'spec_helper'
        
        feature 'smurf completes profile', %q{
        As a smurg
        I want to complete my profile 
        So that I can participate in the community
    } do
    
    
    # Acceptance Criteria
    #* I must specify a name
    #* I must upload a photo
    
    scenario 'smurf specifies all valid info' do
        visit new_smurf_profile_path
        fill_in "Name", with: 'Grumpy'
        attach_file 'Profile Photo', 
            'spec/file_fixtures/test_avatar.jpg
        click_button 'Create Profile'
        
    expect(page).to have_content('Profile Created)
end

    # fill_fixtures directory  (added to the spec/features folder)
    
    Capybara has a file attach command.
    
Outside in development process

    rails g resource smurf_profile
    
    (Dan - like to generate the controller, then the models)
    
    gem 'valid_attribute'
    
    require 'valid_attribute'
    
    Now run model tests
    
Go to Ruby-toolbox to look for file upload gems - Carrierwave

    Goto Gemfile    gem 'carrierwave' 
    
    rails generate uploader 'Something'
    
RMagic  &  MiniMagic (photo manipulations)

ImageMagic

    rails g migration add_profile_photo:string
    
    mount_uploader 
    
    # remember the rails s -p 3xxx (flag)
    
Profile Photo will return an instance of the uploader.

    research the form_for in the docs
    
Watch Railscast on Carrierwave!

It's not a good practice to store files in your database - query time 

Carrierwave speaks well with a gem 'fog' that points to cloud-based storage sites such as AWS, Rackspace, etc.  The community is moving toward "OpenStack" 


