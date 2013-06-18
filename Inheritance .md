##Inheritance: 

AcitveRecord Base

When designing, it's important not to mix-up composition and inheritance 

Inheritance = defines a parent/child relationship

Example:

Car  -- a truck, a SUV, a Van (all are cars)

It passes the "Is a ? test"

####+start( ) is an instance method provided by the classCar

    Car
        +start( )
        +stop( )
        +drive


    Truck
        +openBedDoor
        +dump
        +engage4WheelDrive
        
   # now using the car class a truck has features ()
   
    class Truck < Car
    
    end
    
    Truck.new.start
    
Refactor MissionControl using Inheritance

A Checkin Object & A Checkout Object

Write a new test (find the most basic behavior)

    # acknowledges a new OO 
    
    require_relative 'm c path'

    class MissionControlCommand 
        def initialize 
         @cmd = 'in'
         super          # a reserved word in Ruby -- will call 
         
    # you can run a test on for a specific line (use rb: xx)
    # full-on test refactor creating classes for CheckIn & CheckOut  (eliminates the need for the if/else conditional)
    
    # create a new class for checkout
    
    class MissionControlC
        
        
     protected  #this method can be used or not accessible from outside the world
     def time 
        @time ||= Time.now. '  ' 
     end    


###Encapsulation 

The surface area of an Object  -  (Time.now  cannot reach this method from the outside world )

###Private

Hide internal methods to the outside world 

Private v. Protected 

In Rails (protected will also be hidden from the outside world) 
    
    the Time.now method is 
    
How can I use inheritance to express my Ruby Programs better. 

Created smaller more independently objects (Metz's Bicycle example illustrates this well, too)

Single Responsibility Principle

