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

3. Run the server
```ruby

rails s -b 0.0.0.0

```

4. Naviage to `localhost:3000/projects` and ensure that you can run CRUD operations for the projects

5. Add `root` to `routes.rb`:

```ruby

Rails.application.routes.draw do
  root "projects#index"
  resources :projects
end

```

<details>
  <summary><strong>Self Check Question:</strong> Why did we have to add a root route?</summary>
  <p><blockquote>You can specify what Rails should route '/' to with the root method</blockquote></p>
</details>
<br />

6. Naviage to `localhost:3000/` and ensure that you can still run CRUD operations for the projects

7. Check in your code to GitHub
```bash
$ git add -A
$ git status #Make sure all the new files are tracked AND on stage for being committed!!
$ git commit -m "Added scaffolding"
$ git push
```
