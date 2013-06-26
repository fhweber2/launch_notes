###ABC: Always Be Cloning

Don’t forget, any time you use:

    rake db:migrate 
 
 to make a change to your development database, you’ll need to mirror that change in your test database with 
 
    rake db:test:clone
 
If you run RSpec and get an error about an unknown database, it’s probably because you haven’t cloned yet.
You can chain the two rake tasks together on your command line with:

    rake db:migrate db:test:clone
 
Or you can go one step further and create a shell alias with a shortcut. Use the shortcut 'rmigc; to run a migration and clone the database with a single command.