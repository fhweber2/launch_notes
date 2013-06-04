
    mkdir
    git init
    
_____

Design 

-MC In & MC Out

-A Mission Control Command

-Creates a CheckIn

-Creates a Checkout


Add into /lib

Add a gem set (to get rspec)

    require 'rspec'
    
    
The MC CL Program

start with a #! (shebang)
    
    #!/usr/bin/env ruby
 
    require_relative 'lib/mssion_control_command'      
    
    cmd = MissionControlCommand.new(AEGV[0)    
    puts cmd
    
    



    