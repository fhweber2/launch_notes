
###Order

id:  

name: 

eye color:

User order


    User.order(:id:).all
    User.order(:name).all
    User.order([:name, :id]).first
    
    User.order([:name, :id]).last
    User.order([:name, :id]).all[3]
    
-------

###Constrain

    User.where(:book type, :'non-fiction').all 
    User.where(:book type, :non-fiction, :'eye color' :'blue').all 
    User.where(:book type, :non-fiction, :'eye color' :'blue').where(eye-color :'blue')
    
AREL (can use Ruby instead of using SQL statements)

###These arguments are hashes!  

    {book type: 'non-fiction'}   # in Ruby 1.9
    
    {:book type => 'non-fiction'}  # in Ruby 1.8    
    
    
SQL Injection 
        
    
    
       

    