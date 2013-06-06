###Match

    match '/about_us'  => 'pages#about_us',
        as: :about_us
        
    about_us_path => '/about_us'
        
    # for this to succeed we'll need the following
    # app/controllers/pages.controller
    
        def about_us
        end
        
        app/views/pages/about_us.html.erb
        
    # match scans from top to bottom so order is important
    
    
        
