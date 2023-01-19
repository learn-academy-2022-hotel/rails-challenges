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

Params

As a user, I can visit a page called cubed that takes a number as a param and displays that number cubed.

<h1>
  <%= @number.to_i * @number.to_i * @number.to_i %>
</h1>

As a user, I can visit a page called evenly that takes two numbers as params and displays whether or not the first number is evenly divisible by the second.



As a user, I can visit a page called palindrome that takes a string as a param and displays whether it is a palindrome (the same word forward and backward).
As a user, I can visit a page called madlib that takes params of a noun, verb, adjective, adverb, and displays a short silly story.