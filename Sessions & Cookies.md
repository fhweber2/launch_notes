###Cookies

Can set an Expiry (Key & Value) - specific to a session / timeframe

Using Chrome Inspector:  

Resource Tab --> Cookies --> localhost

Can store items such as:

        session [:user.id] = 6
        session [:cart.id] = 7
    
    # Storing primary keys 
    
Transferring secure data, cc's, username/passwords in an SSL session (in the body) not in any part of the HTTP/GET/POST

Gem for Cookies Testing in Capybara

Ryan Bates Screencast on building encryption 

SQL Injection - Db

Man-in-the Middle - HTTP

Cookie Tampering - Sessions


right a request spec - copy/paste - new file

bundle && rails g rspec:install

require 'spec_helper'

describe 'checkin da box' do

it 'retains a check state across requests'
    visits '/index'
    check 'da box'
    click_button 'do it'
    
    expect(page).to have_selector('input:checked')

    visit '/index
    expect(page).to have_selector('input:checked')
end
  
it 'unchecked a previously 

in the routes file


then in the index_html.file

    <% form_tag do %>
        
    # changed to  <% '/' form_tag method: 'get' %>
    
Rails Docs for FormTags Examples

try session data into session in the browser

    #in the application.html.erb
         <h1> Session </h1>
    
            <%= session %>
        
  ______  

    rails s -p 3002
    
     