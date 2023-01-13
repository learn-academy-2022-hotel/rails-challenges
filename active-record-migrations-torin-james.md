rails new favorite_movies -d postgresql -T
cd favorite_movies
rails db:create
rails generate model Movie title:string category:string
rails db:migrate
rails c

Movie.create(title: 'Superman', category: 'adventure')
Movie.create(title: 'Goodfellas', category: 'drama')
Movie.create(title: 'Jaws', category: 'horror')
Movie.create(title: 'Speed', category: 'thriller')
Movie.create(title: 'Happy Gilmore', category: 'comedy')
 
class AddMovieLength < ActiveRecord::Migration[7.0]
  def change
    add_column :movies, :movie_length, :string
  end
end

rails generate migration add_movie_length
rails db:migrate
rails c

Movie.where(title: 'Superman').update(movie_length: '1:50')
Movie.where(title: 'Goodfellas').update(movie_length: '2:30')
Movie.where(title: 'Jaws').update(movie_length: '1:45')
Movie.where(title: 'Speed').update(movie_length: '1:30')
Movie.where(title: 'Happy Gilmore').update(movie_length: '1:20')

rails generate migration category_to_genre
rails c

class CategoryToGenre < ActiveRecord::Migration[7.0]
  def change
    rename_column :movies, :category, :genre
  end
end

rails db:migrate