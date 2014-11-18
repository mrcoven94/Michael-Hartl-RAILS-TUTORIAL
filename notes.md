#### initialize  & Push to Git repo
```git
$ git init
$ git add -A
$ git commit -m "Initialize repository"
$ git remote add origin git@bitbucket.org:<username>/sample_app.git
$ git push -u origin --all # pushes up the repo and its refs for the first time
```
#### initialize  & Push to Heroku repo
```git
$ git commit -am "Add hello"
$ heroku create
$ git push heroku master
```


#### Undoing things
Even when you’re very careful, things can sometimes go wrong when developing Rails applications. One common scenario is wanting to undo code generation—for example, when you change your mind on the name of a controller and want to eliminate the generated files. Because Rails creates a substantial number of auxiliary files along with the controller, this isn’t as easy as removing the controller file itself; undoing the generation means removing not only the principal generated file, but all the ancillary files as well.  In particular, these two commands cancel each other out:
```ruby
  $ rails generate controller StaticPages home help
  $ rails destroy  controller StaticPages home help
```

Generating a model can be undone by:
```ruby
  $ rails generate model User name:string email:string
  $ rails destroy model User

```



Undoing migrations. Migrations change the state of the database using the command
```ruby
  $ bundle exec rake db:migrate
  $ bundle exec rake db:rollback
```
To go all the way back to the beginning, we can use
```ruby
  $ bundle exec rake db:migrate VERSION=0
```
Substituting any other number for 0 migrates to that version number, where the version numbers come from listing the migrations sequentially.
