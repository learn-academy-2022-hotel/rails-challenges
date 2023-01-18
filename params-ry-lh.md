Params

As a user, I can visit a page called cubed that takes a number as a param and displays that number cubed.

 def greeting
        @name = params[:name]
    end

get '/greeting' => 'main#greeting'

As a user, I can visit a page called evenly that takes two numbers as params and displays whether or not the first number is evenly divisible by the second.

As a user, I can visit a page called palindrome that takes a string as a param and displays whether it is a palindrome (the same word forward and backward).

As a user, I can visit a page called madlib that takes params of a noun, verb, adjective, adverb, and displays a short silly story.
