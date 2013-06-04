%section.container
%h1=post.title
%h2=post.subtitle
    .content
    =post.content
    
for ruby code use an "=" 

    = link_to "back to archive", root_path

        %h1= @post.title
            %p 
             by
             = @post.content
        = @post.content
________

Add Gem

    gem 'haml-rails'
    
Spacing matters (indent 2 spaces) - be consistent






    
    