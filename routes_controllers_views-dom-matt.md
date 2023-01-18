<!-- As a user, I can visit a custom landing page at localhost:3000.
As a user, I can see the names of my team members as hyperlinks on the landing page.
As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.) -->

class TeamController < ApplicationController
    def team_members 
    end
    def dom
    end
    def matt
    end
end

Team Members
<h2> Click on our names to see our top 3 list </h2>
<ul>
<li> Dom </li>
<%= link_to 'Doms Top 3 Movies', '/dom' %>
<li> Matt </li>
<%= link_to 'Matts Top 3 Pizza Spots', '/matt' %>
</ul>

Dom HTML ERB
<h2> Doms Top 3 Movies </h2>
<ul>
<li> Coming to America</li>
<li> Poetic Justice </li>
<li> Footloose </li>
</ul>
<footer> 
<%= link_to 'Back to Home', '/team_members' %>
</footer>

Matt HTML ERB
<h2> Matts Top 3 Pizza Spots</h2>
<ol>
<li> Sisters Pizza </li>
<li> Luigis Pizza </li>
<li> The Pizza Standard </li>
</ol>
<footer> 
<%= link_to 'Back to Home', '/team_members' %>
</footer>

Routes
Rails.application.routes.draw do
  root 'team#team_members'
  get '/dom' => 'team#dom'
  get '/matt' => 'team#matt'
  get '/team_members' => 'team#team_members'
end