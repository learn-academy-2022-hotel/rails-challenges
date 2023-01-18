As a user, I can visit a custom landing page at localhost:3000.
    ```
    rails s
    ```

As a user, I can see the names of my team members as hyperlinks on the landing page.
    ```
    get '/hello' => 'home#hello'
    ```
    ```
    <p>
        <%= link_to 'Raymond', '/raymond' %>
    </p>
    <p>
        <%= link_to 'Moss', '/moss' %>
    </p>
    ```

As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.)
    ```
    get '/favorites' => 'raymond#favorites'
    get '/topthree' => 'moss#topthree'
    ```
    ```
    
    ```