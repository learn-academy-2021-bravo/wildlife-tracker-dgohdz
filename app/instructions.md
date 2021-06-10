Story: As the consumer of the API I can create an animal and save it in the database. An animal has the following information: common name, latin name, kingdom (mammal, insect, etc.).

$ rails generate model Animal common_name:string latin_name:string kingdom:string 

then $rails db:migrate

Story: As the consumer of the API I can list all the animals in a database.

Animal.create common_name:"Lion", latin_name:"Panthera leo", kingdo
m:"Animalia"

Hint: Make a few animals using Rails Console

Story: As the consumer of the API I can update an animal in the database.

Story: As the consumer of the API I can destroy a animal in the database.

Story: As the consumer of the API I can create a sighting of an animal with date (use the datetime datatype), latitude and longitude.

Hint: An animal has_many sightings. (rails g resource Sighting animal_id:integer ...)

Story: As the consumer of the API I can update an animal sighting in the database.

Story: As the consumer of the API I can destroy an animal sighting in the database.
Story: As the consumer of the API, when I view a specific animal, I can also see a list sightings of that animal.
Story: As the consumer of the API, I can run a report to list all sightings during a given time period.
Hint: Your controller can look something like this:
class SightingsController < ApplicationController
  def index
    sightings = Sighting.where(date: params[:start_date]..params[:end_date])
    render json: sightings
  end
end
Remember to add the start_date and end_date to what is permitted in your strong parameters method.

