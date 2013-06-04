##Views

Manipulate the views of the Scaffold.  Incorporate Ruby & Ruby Methods in these views.

A view:  

    app/views  *.html.erb
________

    rails g scaffold xxxx_xxxx name:string etc:string
    
    then rake db:migrate
    
Have two different terminal sessions opened rails s and command line

Open up 

    locatlhost:3000/xxxx_xxxx
    
  Correlate the markup to the View
  
    <p> The time right now is <%= Time.now.to_s %> </p>
    
    % is to alert ruby
    
    = 
    
To comment out ERB 

<%# if false @birds.empty?-%>

<%#end -%>
    
        
