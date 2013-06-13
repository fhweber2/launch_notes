###Deploying an App:

DevOps - scaling and responding to scale

Deployment was very complicated 

In development:  use the gem 'Thin'  (this is similar to Heroku)

"Run locally what you run in production"

Things going on: 

Firewall  Load Balancers  AppServers  Software Proxy(NGINX  Apache)  DBs (slave - reads  &  master - writes )

Software Proxy  (port 80 & port 443) 

This world use to be called System Admin now is DevOps 

Tools "Chef" & "Puppet" - automate deployment 

Using Homebrew to install Apache

Vagrant - simulate a prod environment 

LAMP stack (nginx apache)

###Heroku

Uses EC2 on the backend (spawns requests)

Hard to debug what's happening in the "black box that is AWS - Heroku"

Paying a lot of money for 'at scale' apps.  

RapGenius Article regarding deploying to EC2 and Heroku (http://news.rapgenius.com/James-somers-herokus-ugly-secret-lyrics)

Stand Up the Heroku 
    
    git remote add origin (then the url of the remote)
    
    git push origin master
    
    # its on github
    
    heroku help  # most often used heroku create 
    
    open  #links to heroku
    
-Deployment

-Staging

-Production

    git remote rm heroku
    
    #then
    
    git remote add production git@heroku.com: whatever default assign name
    
You always what to have

    git checkout -b production
    
    git pust origin production
    
    git push production production:master   #
    
Branches are like Slides in a Slide Deck  - use them


Look at gitignore for the database.yml file (git init ignore this file). You do not want this submitted in your deployment - source code.

heroku create (apps are independent of each other)

always start off with:

    git pull origin master
    
then new branch

    rake db:create && !!
    
 root to: pages#index
 
 Need delete files that don't add business value
 



    











