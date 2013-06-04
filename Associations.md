##Relationships:

###has_many

    belongs_to

    has_many
    
    owner
        has_many :books
        
    book
        belongs_to :owner
        
(owner_id) 


    class Song < ActiveRecord::Base
        belongs_to :artist
        belongs_to :album
        
        validates_presence_of   :album
        validates_presence_of   :artist
    end
    
###has_ones
-function the same as has_many, but as a single entity 

Pet Example:
    
Pet - Owner - Account


    class Pet
        belongs_to :owner
    end
______

    class Owner
        has_many :pets
        has_one :account
    end
    
___
    

account.rb

    belongs_to :owner
    
    
Quick Challenge:

    class Song                        
        belongs_to "artist"  
    
        has_many :artists_that_favorited,  
        class_name: 'Artist'
        foreign_key :'favorite_song_id' 
    end

_______

    class Artist
        has_many :songs
        
        belongs_to :favorite_song
        class_name : 'Song'
        foreign_key: 'favorite_song_id'
    end


Migration 

    add_column :artists, :favorite_song_id, :integer



    
    