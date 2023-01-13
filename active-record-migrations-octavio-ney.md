Desktop rails new favorite_movies -d postgresql -T
      create  
      create  README.md
      create  Rakefile
      create  .ruby-version
      create  config.ru
      create  .gitignore
      create  .gitattributes
      create  Gemfile
         run  git init from "."
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /Users/learnacademy/Desktop/favorite_movies/.git/
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/jobs/application_job.rb
      create  app/mailers/application_mailer.rb
      create  app/models/application_record.rb
      create  app/views/layouts/application.html.erb
      create  app/views/layouts/mailer.html.erb
      create  app/views/layouts/mailer.text.erb
      create  app/assets/images
      create  app/assets/images/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/rails
      create  bin/rake
      create  bin/setup
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/cable.yml
      create  config/puma.rb
      create  config/storage.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/assets.rb
      create  config/initializers/content_security_policy.rb
      create  config/initializers/cors.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/new_framework_defaults_7_0.rb
      create  config/initializers/permissions_policy.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/master.key
      append  .gitignore
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/apple-touch-icon-precomposed.png
      create  public/apple-touch-icon.png
      create  public/favicon.ico
      create  public/robots.txt
      create  tmp
      create  tmp/.keep
      create  tmp/pids
      create  tmp/pids/.keep
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor
      create  vendor/.keep
      create  storage
      create  storage/.keep
      create  tmp/storage
      create  tmp/storage/.keep
      remove  config/initializers/cors.rb
      remove  config/initializers/new_framework_defaults_7_0.rb
         run  bundle install
Fetching gem metadata from https://rubygems.org/...........
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Using rake 13.0.6
Using concurrent-ruby 1.1.10
Using websocket-extensions 0.1.5
Using marcel 1.0.2
Using mini_mime 1.1.2
Using racc 1.6.2
Using timeout 0.3.1
Using rack 2.2.5
Using msgpack 1.6.0
Using bundler 2.2.3
Using builder 3.2.4
Using method_source 1.0.0
Using thor 1.2.1
Using zeitwerk 2.6.6
Using pg 1.4.5
Using i18n 1.12.0
Using tzinfo 2.0.5
Using websocket-driver 0.7.5
Using nokogiri 1.14.0 (arm64-darwin)
Using net-protocol 0.2.1
Using rack-test 2.0.2
Using bootsnap 1.15.0
Using sprockets 4.2.0
Using net-pop 0.1.2
Using net-smtp 0.3.3
Using erubi 1.12.0
Using date 3.3.3
Using crass 1.0.6
Using net-imap 0.3.4
Using loofah 2.19.1
Using minitest 5.17.0
Using rails-html-sanitizer 1.4.4
Using activesupport 7.0.4
Using nio4r 2.5.8
Using rails-dom-testing 2.0.3
Using mail 2.8.0.1
Using bindex 0.8.1
Using actionview 7.0.4
Using puma 5.6.5
Using io-console 0.6.0
Using actionpack 7.0.4
Using jbuilder 2.11.5
Using activemodel 7.0.4
Using globalid 1.0.0
Using actioncable 7.0.4
Using activejob 7.0.4
Using activerecord 7.0.4
Using actionmailer 7.0.4
Using sprockets-rails 3.4.2
Using activestorage 7.0.4
Using railties 7.0.4
Using actionmailbox 7.0.4
Using actiontext 7.0.4
Using reline 0.3.2
Using importmap-rails 1.1.5
Using irb 1.6.2
Using stimulus-rails 1.2.1
Using turbo-rails 1.3.2
Using web-console 4.2.0
Using rails 7.0.4
Using debug 1.7.1
Bundle complete! 12 Gemfile dependencies, 61 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
         run  bundle binstubs bundler
       rails  importmap:install
Add Importmap include tags in application layout
      insert  app/views/layouts/application.html.erb
Create application.js module as entrypoint
      create  app/javascript/application.js
Use vendor/javascript for downloaded pins
      create  vendor/javascript
      create  vendor/javascript/.keep
Ensure JavaScript files are in the Sprocket manifest
      append  app/assets/config/manifest.js
Configure importmap paths in config/importmap.rb
      create  config/importmap.rb
Copying binstub
      create  bin/importmap
       rails  turbo:install stimulus:install
Import Turbo
      append  app/javascript/application.js
Pin Turbo
      append  config/importmap.rb
Run turbo:install:redis to switch on Redis and use it in development for turbo streams
Create controllers directory
      create  app/javascript/controllers
      create  app/javascript/controllers/index.js
      create  app/javascript/controllers/application.js
      create  app/javascript/controllers/hello_controller.js
Import Stimulus controllers
      append  app/javascript/application.js
Pin Stimulus
Appending: pin "@hotwired/stimulus", to: "stimulus.min.js", preload: true"
      append  config/importmap.rb
Appending: pin "@hotwired/stimulus-loading", to: "stimulus-loading.js", preload: true
      append  config/importmap.rb
Pin all controllers
Appending: pin_all_from "app/javascript/controllers", under: "controllers"
      append  config/importmap.rb


➜  Desktop cd favorite_movies 









➜  favorite_movies git:(main) ✗ code .  
➜  favorite_movies git:(main) ✗ rails db:create
Created database 'favorite_movies_development'
Created database 'favorite_movies_test'
➜  favorite_movies git:(main) ✗ rails generate model Movie
      invoke  active_record
      create    db/migrate/20230113014122_create_movies.rb
      create    app/models/movie.rb

➜  favorite_movies git:(main) ✗ rails server
=> Booting Puma
=> Rails 7.0.4 application starting in development 
=> Run `bin/rails server --help` for more startup options
Puma starting in single mode...
* Puma version: 5.6.5 (ruby 3.0.0-p0) ("Birdie's Version")
*  Min threads: 5
*  Max threads: 5
*  Environment: development
*          PID: 7264
Exiting
/Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:341:in `initialize': Address already in use - bind(2) for "127.0.0.1" port 3000 (Errno::EADDRINUSE)
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:341:in `new'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:341:in `add_tcp_listener'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:335:in `block in add_tcp_listener'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:334:in `each'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:334:in `add_tcp_listener'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:173:in `block in parse'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:156:in `each'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/binder.rb:156:in `parse'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/runner.rb:156:in `load_and_bind'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/single.rb:44:in `run'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/puma/launcher.rb:193:in `run'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/puma-5.6.5/lib/rack/handler/puma.rb:72:in `run'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/rack-2.2.5/lib/rack/server.rb:327:in `start'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/commands/server/server_command.rb:38:in `start'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/commands/server/server_command.rb:143:in `block in perform'
	from <internal:kernel>:90:in `tap'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/commands/server/server_command.rb:134:in `perform'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/thor-1.2.1/lib/thor/command.rb:27:in `run'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/thor-1.2.1/lib/thor/invocation.rb:127:in `invoke_command'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/thor-1.2.1/lib/thor.rb:392:in `dispatch'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/command/base.rb:87:in `perform'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/command.rb:48:in `invoke'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/commands.rb:18:in `<main>'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/bootsnap-1.15.0/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:32:in `require'
	from /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/bootsnap-1.15.0/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:32:in `require'
	from bin/rails:4:in `<main>'
➜  favorite_movies git:(main) ✗ rails server
=> Booting Puma
=> Rails 7.0.4 application starting in development 
=> Run `bin/rails server --help` for more startup options
Puma starting in single mode...
* Puma version: 5.6.5 (ruby 3.0.0-p0) ("Birdie's Version")
*  Min threads: 5
*  Max threads: 5
*  Environment: development
*          PID: 7308
* Listening on http://127.0.0.1:3000
* Listening on http://[::1]:3000
Use Ctrl-C to stop
Started GET "/" for 127.0.0.1 at 2023-01-12 17:43:17 -0800
   (4.5ms)  CREATE TABLE "schema_migrations" ("version" character varying NOT NULL PRIMARY KEY)
   (2.8ms)  CREATE TABLE "ar_internal_metadata" ("key" character varying NOT NULL PRIMARY KEY, "value" character varying, "created_at" timestamp(6) NOT NULL, "updated_at" timestamp(6) NOT NULL)
  ActiveRecord::SchemaMigration Pluck (0.3ms)  SELECT "schema_migrations"."version" FROM "schema_migrations" ORDER BY "schema_migrations"."version" ASC
  
ActiveRecord::PendingMigrationError (

Migrations are pending. To resolve this issue, run:

        bin/rails db:migrate RAILS_ENV=development

You have 1 pending migration:

20230113014122_create_movies.rb


):
  
activerecord (7.0.4) lib/active_record/migration.rb:627:in `check_pending!'
activerecord (7.0.4) lib/active_record/migration.rb:592:in `block (2 levels) in call'
activesupport (7.0.4) lib/active_support/file_update_checker.rb:83:in `execute'
activerecord (7.0.4) lib/active_record/migration.rb:597:in `block in call'
activerecord (7.0.4) lib/active_record/migration.rb:589:in `synchronize'
activerecord (7.0.4) lib/active_record/migration.rb:589:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/callbacks.rb:27:in `block in call'
activesupport (7.0.4) lib/active_support/callbacks.rb:99:in `run_callbacks'
actionpack (7.0.4) lib/action_dispatch/middleware/callbacks.rb:26:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/executor.rb:14:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/actionable_exceptions.rb:17:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/debug_exceptions.rb:28:in `call'
web-console (4.2.0) lib/web_console/middleware.rb:132:in `call_app'
web-console (4.2.0) lib/web_console/middleware.rb:28:in `block in call'
web-console (4.2.0) lib/web_console/middleware.rb:17:in `catch'
web-console (4.2.0) lib/web_console/middleware.rb:17:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/show_exceptions.rb:26:in `call'
railties (7.0.4) lib/rails/rack/logger.rb:40:in `call_app'
railties (7.0.4) lib/rails/rack/logger.rb:25:in `block in call'
activesupport (7.0.4) lib/active_support/tagged_logging.rb:99:in `block in tagged'
activesupport (7.0.4) lib/active_support/tagged_logging.rb:37:in `tagged'
activesupport (7.0.4) lib/active_support/tagged_logging.rb:99:in `tagged'
railties (7.0.4) lib/rails/rack/logger.rb:25:in `call'
sprockets-rails (3.4.2) lib/sprockets/rails/quiet_assets.rb:13:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/remote_ip.rb:93:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/request_id.rb:26:in `call'
rack (2.2.5) lib/rack/method_override.rb:24:in `call'
rack (2.2.5) lib/rack/runtime.rb:22:in `call'
activesupport (7.0.4) lib/active_support/cache/strategy/local_cache_middleware.rb:29:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/server_timing.rb:61:in `block in call'
actionpack (7.0.4) lib/action_dispatch/middleware/server_timing.rb:26:in `collect_events'
actionpack (7.0.4) lib/action_dispatch/middleware/server_timing.rb:60:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/executor.rb:14:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/static.rb:23:in `call'
rack (2.2.5) lib/rack/sendfile.rb:110:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/host_authorization.rb:137:in `call'
railties (7.0.4) lib/rails/engine.rb:530:in `call'
puma (5.6.5) lib/puma/configuration.rb:252:in `call'
puma (5.6.5) lib/puma/request.rb:77:in `block in handle_request'
puma (5.6.5) lib/puma/thread_pool.rb:340:in `with_force_shutdown'
puma (5.6.5) lib/puma/request.rb:76:in `handle_request'
puma (5.6.5) lib/puma/server.rb:443:in `process_client'
puma (5.6.5) lib/puma/thread_pool.rb:147:in `block in spawn_thread'
Started GET "/" for ::1 at 2023-01-12 17:43:31 -0800
  ActiveRecord::SchemaMigration Pluck (0.2ms)  SELECT "schema_migrations"."version" FROM "schema_migrations" ORDER BY "schema_migrations"."version" ASC
  CACHE ActiveRecord::SchemaMigration Pluck (0.0ms)  SELECT "schema_migrations"."version" FROM "schema_migrations" ORDER BY "schema_migrations"."version" ASC
  
ActiveRecord::PendingMigrationError (

Migrations are pending. To resolve this issue, run:

        bin/rails db:migrate RAILS_ENV=development

You have 1 pending migration:

20230113014122_create_movies.rb


):
  
activerecord (7.0.4) lib/active_record/migration.rb:627:in `check_pending!'
activerecord (7.0.4) lib/active_record/migration.rb:592:in `block (2 levels) in call'
activesupport (7.0.4) lib/active_support/file_update_checker.rb:83:in `execute'
activerecord (7.0.4) lib/active_record/migration.rb:597:in `block in call'
activerecord (7.0.4) lib/active_record/migration.rb:589:in `synchronize'
activerecord (7.0.4) lib/active_record/migration.rb:589:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/callbacks.rb:27:in `block in call'
activesupport (7.0.4) lib/active_support/callbacks.rb:99:in `run_callbacks'
actionpack (7.0.4) lib/action_dispatch/middleware/callbacks.rb:26:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/executor.rb:14:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/actionable_exceptions.rb:17:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/debug_exceptions.rb:28:in `call'
web-console (4.2.0) lib/web_console/middleware.rb:132:in `call_app'
web-console (4.2.0) lib/web_console/middleware.rb:28:in `block in call'
web-console (4.2.0) lib/web_console/middleware.rb:17:in `catch'
web-console (4.2.0) lib/web_console/middleware.rb:17:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/show_exceptions.rb:26:in `call'
railties (7.0.4) lib/rails/rack/logger.rb:40:in `call_app'
railties (7.0.4) lib/rails/rack/logger.rb:25:in `block in call'
activesupport (7.0.4) lib/active_support/tagged_logging.rb:99:in `block in tagged'
activesupport (7.0.4) lib/active_support/tagged_logging.rb:37:in `tagged'
activesupport (7.0.4) lib/active_support/tagged_logging.rb:99:in `tagged'
railties (7.0.4) lib/rails/rack/logger.rb:25:in `call'
sprockets-rails (3.4.2) lib/sprockets/rails/quiet_assets.rb:13:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/remote_ip.rb:93:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/request_id.rb:26:in `call'
rack (2.2.5) lib/rack/method_override.rb:24:in `call'
rack (2.2.5) lib/rack/runtime.rb:22:in `call'
activesupport (7.0.4) lib/active_support/cache/strategy/local_cache_middleware.rb:29:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/server_timing.rb:61:in `block in call'
actionpack (7.0.4) lib/action_dispatch/middleware/server_timing.rb:26:in `collect_events'
actionpack (7.0.4) lib/action_dispatch/middleware/server_timing.rb:60:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/executor.rb:14:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/static.rb:23:in `call'
rack (2.2.5) lib/rack/sendfile.rb:110:in `call'
actionpack (7.0.4) lib/action_dispatch/middleware/host_authorization.rb:137:in `call'
railties (7.0.4) lib/rails/engine.rb:530:in `call'
puma (5.6.5) lib/puma/configuration.rb:252:in `call'
puma (5.6.5) lib/puma/request.rb:77:in `block in handle_request'
puma (5.6.5) lib/puma/thread_pool.rb:340:in `with_force_shutdown'
puma (5.6.5) lib/puma/request.rb:76:in `handle_request'
puma (5.6.5) lib/puma/server.rb:443:in `process_client'
puma (5.6.5) lib/puma/thread_pool.rb:147:in `block in spawn_thread'
Started GET "/" for ::1 at 2023-01-12 17:48:41 -0800
  ActiveRecord::SchemaMigration Pluck (0.4ms)  SELECT "schema_migrations"."version" FROM "schema_migrations" ORDER BY "schema_migrations"."version" ASC
Processing by Rails::WelcomeController#index as HTML
  Rendering /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/templates/rails/welcome/index.html.erb
  Rendered /Users/learnacademy/.rvm/gems/ruby-3.0.0/gems/railties-7.0.4/lib/rails/templates/rails/welcome/index.html.erb (Duration: 0.8ms | Allocations: 461)
Completed 200 OK in 7ms (Views: 1.6ms | ActiveRecord: 0.0ms | Allocations: 4359)









➜  Desktop cd favorite_movies 
➜  favorite_movies git:(main) ✗ rails db:migrate
== 20230113014122 CreateMovies: migrating =====================================
-- create_table(:movies)
   -> 0.0069s
== 20230113014122 CreateMovies: migrated (0.0069s) ============================

➜  favorite_movies git:(main) ✗ rails generate migration add_columns_to_movie
      invoke  active_record
      create    db/migrate/20230113015010_add_columns_to_movie.rb

 Then add_colum methods to function for each column to add
<!-- class AddColumnsToMovie < ActiveRecord::Migration[7.0]
  def change
    add_column :movies, :title, :string
    add_column :movies, :category, :string
  end
end -->




➜  favorite_movies git:(main) ✗ rails db:migrate
== 20230113015010 AddColumnsToMovie: migrating ================================
-- add_column(:movies, :title, :string)
   -> 0.0149s
-- add_column(:movies, :category, :string)
   -> 0.0005s
== 20230113015010 AddColumnsToMovie: migrated (0.0154s) =======================

➜  favorite_movies git:(main) ✗ 
