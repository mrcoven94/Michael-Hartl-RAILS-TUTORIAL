#### Undoing things
Even when you’re very careful, things can sometimes go wrong when developing Rails applications. One common scenario is wanting to undo code generation—for example, when you change your mind on the name of a controller and want to eliminate the generated files. Because Rails creates a substantial number of auxiliary files along with the controller (as seen in Listing 3.4), this isn’t as easy as removing the controller file itself; undoing the generation means removing not only the principal generated file, but all the ancillary files as well. (In fact, as we saw in Section 2.2 and Section 2.3, rails generate can make automatic edits to the routes.rb file, which we also want to undo automatically.) In Rails, this can be accomplished with rails destroy followed by the name of the generated element. In particular, these two commands cancel each other out:
'''
  $ rails generate controller StaticPages home help
  $ rails destroy  controller StaticPages home help
'''

Similarly, in Chapter 6 we’ll generate a model as follows:

  $ rails generate model User name:string email:string
This can be undone using

  $ rails destroy model User
(In this case, it turns out we can omit the other command-line arguments. When you get to Chapter 6, see if you can figure out why.)

Another technique related to models involves undoing migrations, which we saw briefly in Chapter 2 and will see much more of starting in Chapter 6. Migrations change the state of the database using the command

  $ bundle exec rake db:migrate
We can undo a single migration step using

  $ bundle exec rake db:rollback
To go all the way back to the beginning, we can use

  $ bundle exec rake db:migrate VERSION=0
As you might guess, substituting any other number for 0 migrates to that version number, where the version numbers come from listing the migrations sequentially.
