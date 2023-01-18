As a user, I can visit a custom landing page at localhost:3000.
As a user, I can see the names of my team members as hyperlinks on the landing page.
As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.)

MAIN_CONTROLLER.RB :

class MainController < ApplicationController
    def home
    end 
    
    def natally
    end

    def james
    end
end



ROUTES.RB:
Rails.application.routes.draw do

  root"main#home"
  get "/natally" => "main#natally"
  get "/james" => "main#james"
end

HOME.HTML.ERB

<h2> <%= link_to 'Natally', '/natally' %> </h2>
<h2> <%= link_to 'James', '/james' %> </h2>

NATALLY.HTML.ERB

<h2> Natally's favorite activities </h2>
<ul>
<li> Reading </li>
<li> Cooking </li>
<li> Cleaning </li>
</ul>
<%= link_to 'Home', '/' %>


JAMES.HTML.ERB

<h2> James's favorite books </h2>
<ul>
<li> Jurassic Park </li>
<li> Dune </li>
<li> D-Day </li>
</ul>
<%= link_to 'Home', '/' %>




