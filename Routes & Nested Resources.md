
###Nested Resource

config/routes.rb

    resources :apps do
        resources :comments
    end
    
    /apps/4/comments
    /apps/5/comments/5
  
  with a nested route
  
    /apps/:app.id/comments/:id
        params[:apps.id]
        
In Comments Controller:

    def index
        @app = App.find(params[app.id])
        @comments = @app.comments.all
    end
    
For the "show action" with a Helper_method

    class AppsController < ApplicationController
    
        def show
            @app = App.find(params[:id])
        end
        
        helper.method :comments
        protected  # this is not a controller action -it's internal to the class
        
        def comments 
            @comments ||=@app :comments  # means or equals (||=) -hammer
        end
    end
    
    
####.build

    comments_controller.rb
    
        def create
            @app = App.find(params[:app.id])
            @comment = @app.comments.build(params[:comment])
                params[:comment]
                
            @comment.app.id == @app.id 
            
Only have one Controller controlling an action

    config/routes.rb
        
        resource :apps, path: 'applications'
        
        
        new_app_path == 'applications/new'
        
        