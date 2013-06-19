  betacritic git:(user_reviews) subl .
➜  betacritic git:(user_reviews) subl .
➜  betacritic git:(user_reviews) git checkout master
Switched to branch 'master'
➜  betacritic git:(master) git remote
origin
➜  betacritic git:(master) git remote -v
origin	git@github.com:fhweber2/betacritic.git (fetch)
origin	git@github.com:fhweber2/betacritic.git (push)
➜  betacritic git:(master) git remote add upstream
usage: git remote add [<options>] <name> <url>

    -f, --fetch           fetch the remote branches
    --tags                import all tags and associated objects when fetching
                          or do not fetch any tag at all (--no-tags)
    -t, --track <branch>  branch(es) to track
    -m, --master <branch>
                          master branch
    --mirror[=<push|fetch>]
                          set up remote as a mirror to push to or fetch from

➜  betacritic git:(master) git remote add upstream git@github.com:chronophasiac/betacritic.git
➜  betacritic git:(master) git fetch
➜  betacritic git:(master) git remote -f
error: unknown switch `f'
usage: git remote [-v | --verbose]
   or: git remote add [-t <branch>] [-m <master>] [-f] [--tags|--no-tags] [--mirror=<fetch|push>] <name> <url>
   or: git remote rename <old> <new>
   or: git remote remove <name>
   or: git remote set-head <name> (-a | -d | <branch>)
   or: git remote [-v | --verbose] show [-n] <name>
   or: git remote prune [-n | --dry-run] <name>
   or: git remote [-v | --verbose] update [-p | --prune] [(<group> | <remote>)...]
   or: git remote set-branches [--add] <name> <branch>...
   or: git remote set-url [--push] <name> <newurl> [<oldurl>]
   or: git remote set-url --add <name> <newurl>
   or: git remote set-url --delete <name> <url>

    -v, --verbose         be verbose; must be placed before a subcommand

➜  betacritic git:(master) git remote add -f
usage: git remote add [<options>] <name> <url>

    -f, --fetch           fetch the remote branches
    --tags                import all tags and associated objects when fetching
                          or do not fetch any tag at all (--no-tags)
    -t, --track <branch>  branch(es) to track
    -m, --master <branch>
                          master branch
    --mirror[=<push|fetch>]
                          set up remote as a mirror to push to or fetch from

➜  betacritic git:(master) git remote -v
origin	git@github.com:fhweber2/betacritic.git (fetch)
origin	git@github.com:fhweber2/betacritic.git (push)
upstream	git@github.com:chronophasiac/betacritic.git (fetch)
upstream	git@github.com:chronophasiac/betacritic.git (push)
➜  betacritic git:(master) git pull upstream master
remote: Counting objects: 254, done.
remote: Compressing objects: 100% (162/162), done.
Receiving objects: 100% (219/219), 36.35 KiB, done.
remote: Total 219 (delta 91), reused 172 (delta 49)
Resolving deltas: 100% (91/91), completed with 17 local objects.
From github.com:chronophasiac/betacritic
 * branch            master     -> FETCH_HEAD
Updating d8d11d6..918db1e
Fast-forward
 .DS_Store                                                 | Bin 6148 -> 0 bytes
 .gitignore                                                |   3 +
 Gemfile                                                   |   5 +-
 Gemfile.lock                                              |  17 ++
 app/controllers/movies_controller.rb                      |  14 +-
 app/controllers/users_controller.rb                       |   3 +
 app/models/movie.rb                                       |  12 +-
 app/models/user.rb                                        |  27 +++
 app/models/viewing.rb                                     |  15 ++
 app/views/devise/confirmations/new.html.erb               |  16 ++
 .../devise/mailer/confirmation_instructions.html.erb      |   5 +
 .../devise/mailer/reset_password_instructions.html.erb    |   8 +
 app/views/devise/mailer/unlock_instructions.html.erb      |   7 +
 app/views/devise/passwords/edit.html.erb                  |  19 ++
 app/views/devise/passwords/new.html.erb                   |  15 ++
 app/views/devise/registrations/edit.html.erb              |  27 +++
 app/views/devise/registrations/new.html.erb               |  17 ++
 app/views/devise/sessions/new.html.erb                    |  15 ++
 app/views/devise/shared/_links.erb                        |  25 +++
 app/views/devise/unlocks/new.html.erb                     |  16 ++
 app/views/layouts/application.html.erb                    |   2 +-
 app/views/movies/_form.html.erb                           |   3 +-
 app/views/movies/index.html.erb                           |  22 ++-
 app/views/shared/_header.html.erb                         |   9 +-
 app/views/shared/_recently_viewed_movies.html.erb         |  15 ++
 betacritic_ER.graphml                                     | 146 ++++-----------
 config/database.yml                                       |   9 +-
 config/initializers/devise.rb                             | 240 +++++++++++++++++++++++++
 config/locales/devise.en.yml                              |  59 ++++++
 config/routes.rb                                          |   2 +
 db/migrate/20130613182339_devise_create_users.rb          |  46 +++++
 db/migrate/20130617193420_create_viewings.rb              |  10 ++
 db/schema.rb                                              |  28 ++-
 db/seeds.rb                                               |   7 +
 spec/factories.rb                                         |  18 ++
 spec/features/user_adds_movie_spec.rb                     |  29 ++-
 spec/features/user_sees_last_3_movies_looked_at_spec.rb   |  49 +++++
 spec/features/user_sees_movie_spec.rb                     |  24 +++
 spec/features/user_sees_recent_movies_spec.rb             |  11 +-
 spec/features/user_signs_in_spec.rb                       |  25 +++
 spec/features/user_signs_out_spec.rb                      |  19 ++
 spec/features/user_signs_up_spec.rb                       |  19 ++
 spec/models/movie_spec.rb                                 |   6 +-
 spec/models/user_spec.rb                                  |   7 +
 spec/models/viewing_spec.rb                               |  25 +++
 spec/support/factories.rb                                 |   6 -
 46 files changed, 951 insertions(+), 151 deletions(-)
 delete mode 100644 .DS_Store
 create mode 100644 app/controllers/users_controller.rb
 create mode 100644 app/models/user.rb
 create mode 100644 app/models/viewing.rb
 create mode 100644 app/views/devise/confirmations/new.html.erb
 create mode 100644 app/views/devise/mailer/confirmation_instructions.html.erb
 create mode 100644 app/views/devise/mailer/reset_password_instructions.html.erb
 create mode 100644 app/views/devise/mailer/unlock_instructions.html.erb
 create mode 100644 app/views/devise/passwords/edit.html.erb
 create mode 100644 app/views/devise/passwords/new.html.erb
 create mode 100644 app/views/devise/registrations/edit.html.erb
 create mode 100644 app/views/devise/registrations/new.html.erb
 create mode 100644 app/views/devise/sessions/new.html.erb
 create mode 100644 app/views/devise/shared/_links.erb
 create mode 100644 app/views/devise/unlocks/new.html.erb
 create mode 100644 app/views/shared/_recently_viewed_movies.html.erb
 create mode 100644 config/initializers/devise.rb
 create mode 100644 config/locales/devise.en.yml
 create mode 100644 db/migrate/20130613182339_devise_create_users.rb
 create mode 100644 db/migrate/20130617193420_create_viewings.rb
 create mode 100644 spec/factories.rb
 create mode 100644 spec/features/user_sees_last_3_movies_looked_at_spec.rb
 create mode 100644 spec/features/user_sees_movie_spec.rb
 create mode 100644 spec/features/user_signs_in_spec.rb
 create mode 100644 spec/features/user_signs_out_spec.rb
 create mode 100644 spec/features/user_signs_up_spec.rb
 create mode 100644 spec/models/user_spec.rb
 create mode 100644 spec/models/viewing_spec.rb
 delete mode 100644 spec/support/factories.rb
➜  betacritic git:(master) subl .
➜  betacritic git:(master) git checkout -b admin_signin
Switched to a new branch 'admin_signin'
➜  betacritic git:(admin_signin) subl .
➜  betacritic git:(admin_signin) rake db:migrate
Could not find daemons-1.1.9 in any of the sources
Run `bundle install` to install missing gems.
➜  betacritic git:(admin_signin) bundle
Fetching gem metadata from https://rubygems.org/.........
Fetching gem metadata from https://rubygems.org/..
Using rake (10.0.4)
Using i18n (0.6.1)
Using multi_json (1.7.6)
Using activesupport (3.2.13)
Using builder (3.0.4)
Using activemodel (3.2.13)
Using erubis (2.7.0)
Using journey (1.0.4)
Using rack (1.4.5)
Using rack-cache (1.2)
Using rack-test (0.6.2)
Using hike (1.2.3)
Using tilt (1.4.1)
Using sprockets (2.2.2)
Using actionpack (3.2.13)
Using mime-types (1.23)
Using polyglot (0.3.3)
Using treetop (1.4.14)
Using mail (2.5.4)
Using actionmailer (3.2.13)
Using arel (3.0.2)
Using tzinfo (0.3.37)
Using activerecord (3.2.13)
Using activeresource (3.2.13)
Using addressable (2.3.4)
Using bcrypt-ruby (3.0.1)
Using coderay (1.0.9)
Using better_errors (0.7.2)
Using nokogiri (1.5.9)
Using xpath (2.0.0)
Using capybara (2.1.0)
Using chunky_png (1.2.7)
Using coffee-script-source (1.6.2)
Using execjs (1.4.0)
Using coffee-script (2.2.0)
Using rack-ssl (1.3.3)
Using json (1.8.0)
Using rdoc (3.12.2)
Using thor (0.18.1)
Using railties (3.2.13)
Using coffee-rails (3.2.2)
Using fssm (0.2.10)
Using sass (3.2.9)
Using compass (0.12.2)
Using compass-rails (1.0.3)
Installing daemons (1.1.9)
Using orm_adapter (0.4.0)
Using warden (1.2.1)
Using devise (2.2.3)
Using diff-lcs (1.2.4)
Installing eventmachine (1.0.3)
Using factory_girl (4.2.0)
Using factory_girl_rails (4.2.1)
Using jquery-rails (3.0.1)
Using launchy (2.3.0)
Using method_source (0.8.1)
Using pg (0.15.1)
Using slop (3.4.5)
Using pry (0.9.12.2)
Using pry-rails (0.3.0)
Using bundler (1.3.5)
Using rails (3.2.13)
Using rspec-core (2.13.1)
Using rspec-expectations (2.13.0)
Using rspec-mocks (2.13.1)
Using rspec-rails (2.13.2)
Using sass-rails (3.2.6)
Using shoulda-matchers (2.1.0)
Using simple_form (2.1.0)
Installing thin (1.5.1)
Using uglifier (2.1.1)
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
➜  betacritic git:(admin_signin) rake db:migrate
==  DeviseCreateUsers: migrating ==============================================
-- create_table(:users)
NOTICE:  CREATE TABLE will create implicit sequence "users_id_seq" for serial column "users.id"
NOTICE:  CREATE TABLE / PRIMARY KEY will create implicit index "users_pkey" for table "users"
   -> 0.0574s
-- add_index(:users, :email, {:unique=>true})
   -> 0.0062s
-- add_index(:users, :reset_password_token, {:unique=>true})
   -> 0.0049s
==  DeviseCreateUsers: migrated (0.0687s) =====================================

==  CreateViewings: migrating =================================================
-- create_table(:viewings)
NOTICE:  CREATE TABLE will create implicit sequence "viewings_id_seq" for serial column "viewings.id"
NOTICE:  CREATE TABLE / PRIMARY KEY will create implicit index "viewings_pkey" for table "viewings"
   -> 0.0030s
==  CreateViewings: migrated (0.0031s) ========================================

➜  betacritic git:(admin_signin) ✗ rake db:test:prepare
NOTICE:  CREATE TABLE will create implicit sequence "movies_id_seq" for serial column "movies.id"
NOTICE:  CREATE TABLE / PRIMARY KEY will create implicit index "movies_pkey" for table "movies"
NOTICE:  CREATE TABLE will create implicit sequence "users_id_seq" for serial column "users.id"
NOTICE:  CREATE TABLE / PRIMARY KEY will create implicit index "users_pkey" for table "users"
NOTICE:  CREATE TABLE will create implicit sequence "viewings_id_seq" for serial column "viewings.id"
NOTICE:  CREATE TABLE / PRIMARY KEY will create implicit index "viewings_pkey" for table "viewings"
➜  betacritic git:(admin_signin) ✗ rspec spec/features admin_signs_in.rb
No DRb server is running. Running in local process instead ...
/Users/fhweber/.rvm/gems/ruby-1.9.3-p392/gems/rspec-core-2.13.1/lib/rspec/core/configuration.rb:819:in `load': cannot load such file -- /Users/fhweber/Dropbox/Delta/work/betacritic/admin_signs_in.rb (LoadError)
	from /Users/fhweber/.rvm/gems/ruby-1.9.3-p392/gems/rspec-core-2.13.1/lib/rspec/core/configuration.rb:819:in `block in load_spec_files'
	from /Users/fhweber/.rvm/gems/ruby-1.9.3-p392/gems/rspec-core-2.13.1/lib/rspec/core/configuration.rb:819:in `each'
	from /Users/fhweber/.rvm/gems/ruby-1.9.3-p392/gems/rspec-core-2.13.1/lib/rspec/core/configuration.rb:819:in `load_spec_files'
	from /Users/fhweber/.rvm/gems/ruby-1.9.3-p392/gems/rspec-core-2.13.1/lib/rspec/core/command_line.rb:22:in `run'
	from /Users/fhweber/.rvm/gems/ruby-1.9.3-p392/gems/rspec-core-2.13.1/lib/rspec/core/runner.rb:77:in `rescue in run'
	from /Users/fhweber/.rvm/gems/ruby-1.9.3-p392/gems/rspec-core-2.13.1/lib/rspec/core/runner.rb:73:in `run'
	from /Users/fhweber/.rvm/gems/ruby-1.9.3-p392/gems/rspec-core-2.13.1/lib/rspec/core/runner.rb:17:in `block in autorun'
➜  betacritic git:(admin_signin) ✗ rvm use 1.9.3-p392
Using /Users/fhweber/.rvm/gems/ruby-1.9.3-p392
➜  betacritic git:(admin_signin) ✗ rspec
No DRb server is running. Running in local process instead ...
....*.*......F.................

Pending:
  User sees a movie
  As a User
  I want to go to the page for any movie
  so I can see the reviews for the movie
   User sees reviews for the movie
    # Not yet implemented
    # ./spec/features/user_sees_movie_spec.rb:22
  User adds a movie
  As a User
  I want to add a movie for review
  so I can review it later
   User browses movies alphabetically
    # Not yet implemented
    # ./spec/features/user_adds_movie_spec.rb:71

Failures:

  1) Admin signs in
  As a registered user with admin privileges,
  I should be able to login and be an admin
  So I can have admin privileges on the site
   Admin can sign in from the landing page
     Failure/Error: fill_in 'user[password_confirmation]', :with => 'qwertyuiop'
     Capybara::ElementNotFound:
       Unable to find field "user[password_confirmation]"
     # ./spec/features/admin_signs_in_spec.rb:14:in `block (2 levels) in <top (required)>'

Finished in 1.93 seconds
31 examples, 1 failure, 2 pending

Failed examples:

rspec ./spec/features/admin_signs_in_spec.rb:9 # Admin signs in
  As a registered user with admin privileges,
  I should be able to login and be an admin
  So I can have admin privileges on the site
   Admin can sign in from the landing page

Randomized with seed 39907

➜  betacritic git:(admin_signin) ✗ rvm current
ruby-1.9.3-p392
➜  betacritic git:(admin_signin) ✗ rvm list

rvm rubies

   jruby-1.7.3 [ x86_64 ]
   ruby-1.9.3-head [ x86_64 ]
=> ruby-1.9.3-p392 [ x86_64 ]
 * ruby-1.9.3-p429 [ x86_64 ]

# => - current
# =* - current && default
#  * - default

➜  betacritic git:(admin_signin) ✗ bundle
Fetching gem metadata from https://rubygems.org/.........
Fetching gem metadata from https://rubygems.org/..
Resolving dependencies...
Using rake (10.0.4)
Using i18n (0.6.1)
Using multi_json (1.7.6)
Using activesupport (3.2.13)
Using builder (3.0.4)
Using activemodel (3.2.13)
Using erubis (2.7.0)
Using journey (1.0.4)
Using rack (1.4.5)
Using rack-cache (1.2)
Using rack-test (0.6.2)
Using hike (1.2.3)
Using tilt (1.4.1)
Using sprockets (2.2.2)
Using actionpack (3.2.13)
Using mime-types (1.23)
Using polyglot (0.3.3)
Using treetop (1.4.14)
Using mail (2.5.4)
Using actionmailer (3.2.13)
Using arel (3.0.2)
Using tzinfo (0.3.37)
Using activerecord (3.2.13)
Using activeresource (3.2.13)
Using addressable (2.3.4)
Using bcrypt-ruby (3.0.1)
Using coderay (1.0.9)
Using better_errors (0.7.2)
Using bundler (1.3.5)
Installing cancan (1.6.10)
Using nokogiri (1.5.9)
Using xpath (2.0.0)
Using capybara (2.1.0)
Using chunky_png (1.2.7)
Using coffee-script-source (1.6.2)
Using execjs (1.4.0)
Using coffee-script (2.2.0)
Using rack-ssl (1.3.3)
Using json (1.8.0)
Using rdoc (3.12.2)
Using thor (0.18.1)
Using railties (3.2.13)
Using coffee-rails (3.2.2)
Using fssm (0.2.10)
Using sass (3.2.9)
Using compass (0.12.2)
Using compass-rails (1.0.3)
Using daemons (1.1.9)
Using orm_adapter (0.4.0)
Using warden (1.2.1)
Using devise (2.2.3)
Using diff-lcs (1.2.4)
Using eventmachine (1.0.3)
Using factory_girl (4.2.0)
Using factory_girl_rails (4.2.1)
Using jquery-rails (3.0.1)
Using launchy (2.3.0)
Using method_source (0.8.1)
Using pg (0.15.1)
Using slop (3.4.5)
Using pry (0.9.12.2)
Using pry-rails (0.3.0)
Using rails (3.2.13)
Using rspec-core (2.13.1)
Using rspec-expectations (2.13.0)
Using rspec-mocks (2.13.1)
Using rspec-rails (2.13.2)
Using sass-rails (3.2.6)
Using shoulda-matchers (2.1.0)
Using simple_form (2.1.0)
Using thin (1.5.1)
Using uglifier (2.1.1)
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
➜  betacritic git:(admin_signin) ✗ git init
Reinitialized existing Git repository in /Users/fhweber/Dropbox/Delta/work/betacritic/.git/
➜  betacritic git:(admin_signin) ✗ git status
# On branch admin_signin
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#	modified:   Gemfile
#	modified:   Gemfile.lock
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	.ruby-version.rb
#	spec/features/admin_signs_in_spec.rb
no changes added to commit (use "git add" and/or "git commit -a")
➜  betacritic git:(admin_signin) ✗