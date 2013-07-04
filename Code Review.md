in - memory sorting

in - memory constraining 

    sort { }  => order
    
    sort { } => where
    
Rely on the tools for SQL 
    
 For Tests:
 
 **Use Assertions
 
 
 Javascript Testing 
 
 Konacha?   
 
 
#### More from Code Review:  (July 2nd)

Impersonation Attacks
    
    POST to /users/8/comments
    
nesting resources under users

    # refactor to
    
    POST to /comments => use current_user
    
#####Controller

    # in the controller 
    
    --Bad
        def create 
            @user = User.find(params[:usdr_id])
            @comment = @user.comments.build
            
        end
        
    --Good
    
            @comment = current_user.comments.build
            
#####VCR for test suites (service's throttle maps or geocodes )

Extracting To Scopes
(models handle biz - tell don't ask in controllers)

Favor Class Methods over Scope (when we use a scope keyword we invoke implementation)

    --Bad
  
    comment.where(user_id:4).where(created_at: 7.days.ago)
    
    --Good
    
    current_user.comments.recent 
    
    --Class Method
    
        class  << self
            def recent
                where(created_at:7.days.ago)
            end
        end
__________

    @comment = current_user.comments.new
    
______

####Security Considerations

    attr_accessible :role       
    
    # be careful here with mass assignment (possible security violation)
    
    


    
    





    
    
        
    
        
    

 