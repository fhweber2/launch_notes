##project:  Launchly

    describe "launchly short url"
        it "allows us to create a shortened url" do
            visit new_launchly_path 
            fill_in 'Url', with! 'http://google.com'
            expect(page).to have_content('Launchly Link Created')
        end
    end

####Capybara

Save/Open Page

    save_and_open_page
    
A good test from Apollo:

        require 'spec_helper'

    describe "Events" do
        describe "Viewing individual Events" do
            it "should display an individual event" do
                event = Event.create!(:location => "my backyard")
                get event_path(event.id)
                expect(response.status).to eq(200)
                end
            end
         end