#### Configure Git
```git
$ git config --global user.name "Your Name"
$ git config --global user.email your.email@example.com
$ git config --global push.default matching
$ git config --global alias.co checkout
```
#### Configure BitBucket
1. Sign up for a Bitbucket account if you don’t already have one.
2. Copy your public key to your clipboard. As indicated in Listing 1.11, users of the cloud IDE can view their public key using the cat command, which can then be selected and copied. If you’re using your own system and see no output when running the command in Listing 1.11, follow the instructions on how to install a public key on your Bitbucket account.
3. Add your public key to Bitbucket by clicking on the avatar image in the upper right and selecting “Manage account” and then “SSH keys” 
4. Create” to create a new repository 
5. Leave the box next to “This is a private repository.” checked. 
6. After clicking “Create repository”, follow the instructions under “Command line > I have an existing project”
7. When pushing up the repository, answer yes if you see the question “Are you sure you want to continue connecting (yes/no)?”

Listing 1.11 
```git 
$ cat ~/.ssh/id_rsa.pub
```
Adding Bitbucket and pushing up the repository.
```git 
$ git remote add origin git@bitbucket.org:<username>/hello_app.git
$ git push -u origin --all # pushes up the repo and its refs for the first time
```

#### Configure Heroku
```git
$ heroku version
$ heroku login
$ heroku keys:add
```
Creating a new application at Heroku.
```
$ heroku create
git push heroku master
```

#### initialize  & Push to Git repo
```git
$ git init
$ git add -A
$ git commit -m "Initialize repository"
$ git remote add origin git@bitbucket.org:<username>/sample_app.git
$ git push -u origin --all # pushes up the repo and its refs for the first time
```
#### Push to Heroku repo
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
