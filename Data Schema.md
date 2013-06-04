Check Out Numarex's Db Scheme:

http://dev.numerex.com/images/uploads/foundation_schema.png


RailsRoad 


Unique Indexs for Tables, e.g. 

    validates_uniqueness_email  
    
Dan recommends an the expressive form of validations e.g,

    validates :name, presence :true
    
refactor to:
    
    validates_presence_of :name
    
    