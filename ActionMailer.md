###ActionMailer

Can - SPAM

-Specify mailing address

-Opt-Out

-Confirmation of opt-in


SendGrid 

PostmarkApp

The need to evaluate gems and 3rd party libraries.  As for SaaS, follow the pack (look for reviews, etc. then execute)

####Outsource non-core infrastructure as much as you can.  So, you can focus on your core. 



copy your config.rb file for Staging 'ENV'

Mailcatcher 

localhost:1080 (Mailcatcher UI)

Unit tests (email.spec) a good read me (github) - a ton of resources for this .spec

Acceptance Test (capybara)

email client testing - litmus (local company)

heroku (help config)


class Acceptance < ActionMailler::Base
    default from: "from@example.com"
    
    def notification(email)
        @the_date = Time,now
        @email
    
    
    
    
    Hello <%= @receipent %>

    Today is <%= @the_date %> and you're totally in! 

    Sincerely,

    Clown President
 