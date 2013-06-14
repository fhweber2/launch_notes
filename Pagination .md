Pagination

gem Kaminiari 

Kaminari :  https://github.com/amatsuda/kaminari


write the specs

    user_views_paginated_xxx_xxx
    
_______

require 'spec_helper'

    describe 'a user sees as paginates list of app', %q{
    
    As a user
    I want to view a paginated list of apps
    So that I don't get overwhelmed

} do

 it 'displays a paginated list of apps' dp
    visits apps_path
    expect(page).to  have_content app1.name
    expect(page).to_not  have_content app2.name
    
    clickk_link "Next"
    
    expect(page).to  have_content   app1.name
    expect(page).to  have_content   app2.name
    
    
    de index
        @apps = App.order(params[])

