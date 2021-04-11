## Part 0 (A): Preparation: get your app running locally

```sh
$ cd /root/
$ git clone https://github.com/{YOURGITHUBUSERNAME}/{YOURREPONAME}.git # Replace YOURGITHUBUSERNAME with your github username and replace YOURREPONAME with the name of your repo.
```
Now that you have repo cloned from GitHub. CD into `YOURREPONAME`. 

After you are in your `YOURREPONAME` directory. Run `rails new .` This command will install a new Ruby on Rails application in the current directory.

Copy and paste the following line into your projects Gemfile on `line 30`. 

```
group :production do
  gem 'pg', '~> 0.21' # for Heroku deployment
  gem 'rails_12factor'
end
```

Whenever you start working on a Rails project, the first thing you should do is to run Bundler, to make sure all the app's gems are installed.  Switch to the app's root directory and run `bundle install --without production` (you only need to specify `--without production` the first time, as this setting will be remembered on future runs of Bundler for this project).

Finally, get the local database created:

```sh
$ rake db:migrate
```

<details>
  <summary><strong>Self Check Question:</strong> How does Rails decide where and how to create the development database?  (Hint: check the <code>db</code> and <code>config</code> subdirectories)</summary>
  <p><blockquote>The <code>rake db:migrate</code> command creates a local development database (following the specifications in <code>config/database.yml</code>) and runs the migrations in <code>db/migrate</code> to create the app's schema.  It also creates/updates the file <code>db/schema.rb</code> to reflect the latest database schema.  <strong>Note: it's important to keep this file under version control.</strong> </blockquote></p>
</details>
<br />

<details>
  <summary><strong>Self Check Question:</strong> What tables got created by the migrations?</summary>
  <p><blockquote>The <code>movies</code> table itself and the rails-internal <code>schema_migrations</code> table that records which migrations have been run.</blockquote></p>
</details>
<br />


At this point you should be able to run the app locally (`rails server -b 0.0.0.0`) and navigate to `http://localhost:3000` in your browser.  

Note: If you stop the server by hitting control-C, you will no longer be able to visit the Ruby on Rails site. Start the server again by repeating the last command. 

Lastly, push the new application to Github. 
```sh
cd /root/{YOURPOJECTNAME}
git add -A
git status //Make sure all the new files are tracked AND on stage for being committed!!
git commit -m “Init"
git push origin master
```
