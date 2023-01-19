Create a new Rails app in the appropriate folder: 
    $ rails new routes_controllers_views_params -d postgresql -T
    $ cd routes_controllers_views_params
Create a database: 
    $ rails db:create
Begin the rails server: 
    $ rails server
In a browser navigate to: 
    http://localhost:3000

Create a controller 
    $ rails generate controller Main
Add route to config/routes.db (file is created when running rails new)
    Format:
    HTTP verb 'url' => 'name_of_controller#name_of_method_found_in_controller'
    Example:
    root 'main#team_members'
    get '/team_members' => 'main#team_members'
Add method to controller:
    In app/controllers/main_controller.rb:
    def team_members
    end
Add view:
    In app/views/main folder
    Create a file called team_members.html.erb
    Add:
    <%= link_to 'Octavio', '/favorite_things_octavio' %>
    <%= link_to 'Torin', '/favorite_things_torin' %>

params CHALLENGES
Add route:
    get '/cubed' => 'main#cubed' 
    # http://localhost:3000/cubed?number=5
    get '/cubed/:number' => 'main#cubed'
Add method:
    class MainController < ApplicationController
        def team_members 
            # render html: 'Torin'
        end

        def cubed
            @number = params[:number]
        end
    end
Add view file:
    app/views/main/cubed.html.erb
    Add content to cubed.html.erb file:
    <h1> Cube my numbrrr : <%=@number%> </h1>
    <h2> <%= @number.to_i**3 %> </h2>
