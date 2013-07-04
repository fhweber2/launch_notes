###OAuth 

Rack:  

<http://railscasts.com/episodes?utf8=%E2%9C%93&search=rack>

The Rack Docs:

<http://rack.rubyforge.org/doc/>

<http://guides.rubyonrails.org/rails_on_rack.html>

The Docs: 

<http://oauth.net/documentation/>

 RFC 5849: 
 
 <http://tools.ietf.org/html/rfc5849>
 
 Omniauth: 
 
 <http://railscasts.com/episodes?utf8=%E2%9C%93&search=omniauth>
 
 
 
    class User
        has_many :identifiers 
        
    class Identity
        provider
        uid
        
        