As Rails Devs we like rules!  Conventions!

###State Machines

a series of 'states' and 'transitions'  

moving objects through 

example of Gazelle.com  around the sale of a mobile device

    state  :estimated
    state  :submitted
    state  :pending_shipment
    
the need for a workflow type solution states machines are the way

look at the documentation from the 'gem'

Workflow Branches:

received  -->  inspected
                                                    |
                                                    
                                        awaiting confirmation 
                                                                           
                                                                                |
                                                                            
                                                                            accept 
                                                                            
                                                                                    |
                                                                                    
                                                                                    decline -->    returned
                                                                                    
    To possibly use in the Breakable Toy - this would be good for the improvements / capex / accounts 


RailsCasts:

http://railscasts.com/episodes/392-a-tour-of-state-machines

