Setup
Create a new Rails application called 'favorite_movies'.
Create the database
Generate a Movie model with a title attribute and a category attribute
- rails new favorite_movies -d postgresql -T
- cd favorite_movies
- rails db:create
- rails generate model Movie title:string category:string
- rails db:migrate 
- rails c
- Movies.all


Challenges
Add five entries to the database via the Rails console
Create a migration to add a new column to the database called movie_length
Update the values of the five existing attributes to include a movie_length value
Generate a migration to rename the column 'category' to 'genre'