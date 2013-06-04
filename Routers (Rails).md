##Routers

Dissecting the magic that is the router

    GET '/'

DNS & HTTP Request -  HTTP Response (Header and Body)

In Rails

    HTTP Request --> Router --> Controller --> View -->HTTP Response
    
    In the Header: session cookies, code e.g 200, DTG, etc
   
Representational State Transfer (REST)

    #config/routes.rb
        resources :issues
        
        Paths      HTTP Op     Controller#Action
     
        /issues         GET         issues#index        RETRIEVE
        /issues/:id     GET         issues#show         RETRIEVE
        /issues/:id/edit GET        issues#edit
        /issues/:id/new GET         issues#new
        /issues         POST         issues#create      CREATE
        /issues/:id     PUT          issues#update      UPDATE
        /issues/:id     Delete       issues #destroy    DELETE
        
gems:  friendly (hacks the Rails Core, though)

    #config/routes.rb
        resources :issues, only: :index
        
Route mapping: there's a strong correlation to the paths URL (when writing an API)

REST operations matching to the database 

Create a correlating Resource (HTTP) for this Model (Db)


    HTTP Status Codes
    
    200 - Success!  Yay
    404 - Resource Missing (shit)
    500 - Server Error (oh shit)
    302/
    301 - Redirect
    
###Conclusion (The Rails Way):

• Recognizing incoming requests and mapping them to a corresponding controller action, along with any additional variable receptors

• Recognizing URL parameters in methods such as link_to and matching them up to a corresponding route so that proper HTML links can be generated
        