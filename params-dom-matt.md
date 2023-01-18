class TeamController < ApplicationController
    def team_members 
    end
    def dom
    end
    def matt
    end
    def cubed
        @number = params[:number]
        @result = params[:number] * 3
    end
end

cubed html erb
number is : <%= @result %>