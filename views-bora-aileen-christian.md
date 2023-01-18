Review
The routes.rb file defines all the possible urls to which your application is prepared to respond. It's like the address book of your Rails app.
Each route will point to a method on in the controller file.
The controller method will ultimately do the work you require and send the appropriate view response.
params is a method returning a ActionController::Parameters which is a hash of parameters submitted in the request.


Challenges
Routes, Views, Controllers

As a user, I can visit a custom landing page at localhost:3000.

localhost:3000/team_members

def team_members
        render html: 'Bora Ros, Aileen Whitney, Christian Snyder'
end

get '/team_members' => 'main#team_members'

As a user, I can see the names of my team members as hyperlinks on the landing page.

<p>
<a href="https://google.com">Bora Ros</a>
<a href="https://slack.com">Aileen Whitney</a>
<a href="https://discord.com">Christian Snyder</a>
</p>

As a user, I can click on each team member's name and be taken to a page that displays a list of that team member's top three things. (Could be top three restaurants, activities, books, video games, hiking locations, beaches, doughnut shoppes, movies, etc.)

