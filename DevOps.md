###DevOps

Things to do to get your Rails App up on S3

ssh keys

install an instance of Ruby on my AWS "cool server"'

then install Apache

Package 'yum' (apache postgres, etc)

    sudo yum install ...
    
    # then ps aux
    
    sudo service httpd service start?
    
Remember Port 22 - SSH 

Add HTTP Port 80

via the Security Group on AWS Mgmt Console

Download all of the Ruby dependencies (ssl libraries, etc.)

Rails can only take one instance at a time -- on port:80

Apache can use a Round Robin with multiple thin servers ( 2 ports )

    sudo service postgresql start
    
    psql task list something  # make yourself an admin , add a user , etc
    
Installing Chef




