###Queues:
 
 Request and Response from the client - server  --> external services API, SMTP, DB
 
 Scheduling a time for the request/response 
 
 Some tools in Rails:
 
 delay-job  (ActiveRecord)
 resque (reddis)  - has file system persistence  
 sidekiq 
 
 User Signs up for a service


####queue:

+send-emailsign up 
+send - forgotten password
+perform-api-request 

####worker:


resque - email (apply the job server to send emails)  

https://github.com/resque/resque

Deployment  

Heroku by default only provides a web-worker process

Config our jobs in production to run inline

Production/Development Server (mentor's to assist in system setup)






