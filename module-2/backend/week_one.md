## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
  -GET : reads from a resource
  -POST : creates a resource
  -PUT :updates all of a resource
  -DELETE :destroys a resource
  -PATCH : updates just a part of a resource

2. What is Sinatra?
Sinatra is a Domain Specific Language that helps us to write web applications.

3. What is MVC?  
It's the Model, View and Controller pattern or model that we use to better organize our code. It is divided in   
	- Model: What interacts with the database and has behaviors
	- View: what is shown to the user
	- Controller: sort of the "middle-man". It interacts with the model to provide the user with the view


4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
To follow the RESTful convention, since REST is standard across web applications.

5. What types of variables are accessible in our view templates without explicitly passing them?  
Instance variables

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?


  ```ruby
  get '/horses' do
    erb :index
  end
  ```
  
  I would do :
  ```ruby
  get '/horses' do
	@count = 1
    erb :index
  end
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

  I would do :
  ```ruby
  get '/horses' do
	@count = 1
    erb :index, :locals => {:name => "Mr.Ed"}
  end
  ```

9. What's the purpose of ERB?
It allows us to use Embedded Ruby (hence the name)  alongside html.

10. Why do I need a development AND test database?
To avoid polluting your actual database and to make your application easier to test.

11. What is CRUD and why is it important?
It stands for Create, Read, Update and Destroy. They are the functions that we use to interact with resources. They are important because they remind us of what we need to do to build a functional application. For example, when building the Laugh Tracks application, I was forgetting to allow a "delete" option for each comedian. Keeping CRUD in mind, I was able to remember to add that in.

12. What does HTTP stand for?
HyperText Transfer Protocol 

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
You can do <%       %> or <%=       %>. The first one is used to just execute what's inside the tags, while the second one is used to both execute and print it. 

14. What's an ORM? What does it do?
It's an Object Relational Mapper. It's used to take a database and create objects from it. The rows of a table are an instance of an object and the columns are the attributes. It makes it easier to work with databases.


15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
ActiveRecord

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
	- get '/restaurants' :  to see all restaurants
	- get '/restaurants/:id': to see restaurant with that id 
	- get '/restaurants/new': to pull form to create a new restaurant
	- post '/restaurants':  to create (save) the new restaurant
	- get '/restaurants/:id/edit': to pull form to edit restaurant with that id
	- put '/restaurants/:id': to update restaurant with that id
	- delete '/restaurants/:id' : to destroy restaurant with that id

17. What's a migration?
It's an intended change to a database.

18. When you create a migration, does it automatically modify your database?
No, it does not. It's just the set of instructions. 

19. How does a model relate to a database?
A model takes information from a database to do its job.

20. What is the difference between `#new` and `#create`?
Both are ActiveRecord methods. #new creates a new instance of an object but doesn't save it to the database. #create creates a new instance and then saves it to the database.

21. Given a table named `animals`, What is the SQL query that will return all info from that table?
    `id     name        number_of_legs
    -----   ------      --------------
      1     panda       4
      2     giraffe     4
      3     whale       0
      4     bird        2
    `

SELECT * FROM animals;

22. Using the same table, What is the SQL query that will return only the animals that has 4 legs?

SELECT * FROM animals WHERE number_of_legs = 4;

### Review Questions:  
22. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  

```
CSV.foreach("films.csv", headers: true, header_converters: :symbol) do |row|
Film.create(:title => row[:title], :description => row[:description])
```


23. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?

```
activities[:hiking][:supplies] << "granola"
```

24. What are the 4 Principles of OOP? Give a one sentence explanation of each.

-Encapsulation: Each object keeps its state private, within a class.
-Abstraction: Each object should only expose its functionality at a high level, making things simpler at each step and hiding the inner workings of it all.
-Inheritance: a class can inherit attributes and/or methods from its parent class.
-Polymorphism: two or more methods can share the same name but act differently, depending on their class

### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel overwhelmed by the content presented this week
