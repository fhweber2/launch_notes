Modules  Enumerable

    class UserSet
        include Enumerable
        attr_accessor :users 
        delegate :each, :to =>.users
        
        def each
        
        end
    end
    
Works best in an abstraction 

valid ruby syntax (balance items 1 on 1 or 2 on 2 , etc)  e.g.

    @first_name @last_name = first_name , last_name
    
    