# Part 1a - Scaffolding with Rails 

Beginners introduction to scaffolding with Ruby on Rails. 


## Generate the scaffold

1. Generate the scaffold for the 'Projects' model, view, controller. 

```ruby

rails generate scaffold projects title:string description:text

```

2. Migrate the database: 
```ruby
rake db:migrate
```

3. Run the server `rails s -b 0.0.0.0`

4. Naviage to `localhost:3000/projects` and ensure that you can run CRUD operations for the projects

5. Add `root` to `routes.rb`:

```ruby

Rails.application.routes.draw do
  root "projects#index"
  resources :projects
end

```

6. Naviage to `localhost:3000/` and ensure that you can still run CRUD operations for the projects

7. Check in your code to GitHub
