Challenges
Routes, Views, Controllers

As a user, I can visit a custom landing page at localhost:3000.

In homepage_controller.rb:
class HomepageController < ApplicationController
    def welcome
    end
end

In app/views/homepage/welcome.html.erb
<h1>Welcome to our homepage!</h1>

In routes.rb
Rails.application.routes.draw do
  get '/' => 'homepage#welcome'
end

As a user, I can see the names of my team members as hyperlinks on the landing page.

<a href='url'>Molly</a>
<a href='url'>Chris</a>

As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.)

<ul>
  <li>React</li>
  <li>Jest</li>
  <li>RSpec</li>
</ul>

  get '/molly' => 'homepage#molly_favorites'
  get '/chris' => 'homepage#chris_favorites'

class HomepageController < ApplicationController
    def welcome
    end
    def molly_favorites
    end
    def chris_favorites
    end
end