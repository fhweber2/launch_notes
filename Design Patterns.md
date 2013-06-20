###Design Patterns:  

"Standing on the Shoulders of Giants"  

Common Architectural Designs  -  Strong Object Orientation 

Methods Small
Classes Independent

####SOLID

The next chapter - will take you from beginner to intermediate 

Favoring Composition over Inherieence


    class AnimalEmote
        def initialize(animal)
            @animal = animal
        end
        
        def emote
            adapter_for(@animal).emote
            
         
####The Adapter Pattern

Getting rid of conditionals and using an adapter is considered cleaner code (still have to test the adapter module)


####Design Patterns in Ruby (see more):

https://github.com/nslocum/design-patterns-in-ruby#observer


Adapters:  Convert the interface of a class into another interface clients expect. An adapter lets classes work together that could not otherwise because of incompatible interfaces.

 "S" = Single Responsibility 
 
 Liskov Substitution (every child of the 'emote' adapter needs to have this behavior)
 
 
###Listeners 

Tap (check this out)


 
