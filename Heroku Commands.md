###Heroku Commands:

Processes:

    heroku ps  # status of remote processes (process state)
     
Troubleshoot:
    
    heroku logs  # allows a stack trace 
    
    heroku run rake db:migrate  # running migrations on the heroku server
    

Maintenance: 
  
    heroku run console  # similar to rails c
    
    heroku apps   # shows all remote app servers tied to the account
    
    heroku destroy  # provide app name (manually) then bam!
    
Merging Git:

    git remote add <remote_name> <remote_url>
    
Branches: 

It's a good idea to manage a branch that directly reflects what is currently in production. You could do this the following way from the master branch:
    
    git checkout -b production
    git merge master
    git push heroku production:master

Dbs: 

Heroku ignores the database.yml file, and generates one on its own. Since you need one for development and test, you should make sure that database.yml is not in git using .gitignore (this is good practice in any case).
To do this:
    
####Copy your config/database.yml to config/database.example.yml. Remove any sensitive credentials

####Remove your config/database.yml

####Commit these changes

####Add config/database.yml to your .gitignore

####Copy config/database.example.yml to config/database.yml and make any necessary changes to restore database connectivity. 

####Since the file has been added to your .gitignore, it should no longer show up as a modified file in a git context.


    
      
        
     
    