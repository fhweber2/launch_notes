###Composition:

Favor Composition over inheritance 

Module
-share behavior amongst classes + object

-organize code

    /admin/users
    /users
    
module Admin
    class UsersController
    end
    
 #  some syntax 
 
     Admin::UsersController
            
    namespace

Convention over Configuration - may have to rename your tables as Rails will want to override.

    class Admin::UsersController
        include     AdminFunctions
        extend      AdminFilters # class methods - additional
    end
    
Naming of a Module is as equally important as a Class

You can nest Modules within Modules

Guideline: do not create a module unless you need to run something twice (shared behavior), only where there is repetition. 

Inheritance v. Modules (when weighing a decision about either of these, use Modules)



