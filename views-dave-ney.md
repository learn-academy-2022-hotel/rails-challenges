class MainController < ApplicationController
    
    def dave
        render 'dave.html.erb'
    end
end


<h2> hi </h2>


Rails.application.routes.draw do
  # Define your application routes per the DSL in https://guides.rubyonrails.org/routing.html

  # Defines the root path route ("/")
  # root "articles#index"
  root 'main#custom'
  get '/custom' => 'main#custom'
  get '/dave' => 'main#dave'

end

<h1> 'Custom landing page yo' </h1>

<p> <%= link_to 'Dave!', '/dave' %> <%= link_to 'Ney!', '/ney' %>  </p>

