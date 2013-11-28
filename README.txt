# Download rails from railsinstaller.org/en and install it.

# Create new rails application named myApp 
# rails will create the application in a new sub-directory named myApp
rails new myApp

# change directory to myApp
cd myApp

# Create a new database for the app
rake db:create

# Add an object named obj1 with attributes str1, text1, bool1
rails generate scaffold obj1 str1:string text1:text bool1:boolean

# Apply new changes to the database after each change
rake db:migrate

# Create a new local git repo
git init

# Add your new rails application directory to git
git add .

# Commit your changes to the local git repo
git commit -m "Initial commit of rails application myApp"

# Create a github acct, then a git repo there, then add it's URL like this
git remote add origin https://github.com/brucelhill/devImpact1.git

# Push changes up to cloud
git push -u origin master

# Start rails web server
rails server
# View web page for instances of your first object, obj1
http://localhost:3000/obj1s

# Bundler is an app that keeps track of the code dependencies via git
# For ruby, these dependent packages are called rubygems
bundle

# New collaborators need to create their own database (will share them later)
rake db:create:all
# and migrate the stuff we just pulled from git into the db
rake db:migrate

# GUI design tool is Bootstrap
# Download from getbootstrap.com
# Install instructions at railsapps.github.io/twitter-bootstrap-rails.html

cp bootstrap-3.0.2-dist/dist/js/bootstrap.js myApp/public/javascripts/
cp bootstrap-3.0.2-dist/dist/css/*.css		 myApp/public/stylesheets/
cp bootstrap-3.0.2-dist/dist/fonts/*		 myApp/public/images/

# Add the following line to myApp/Gemfile
gem 'bootstrap-sass'

# Install it via
bundle install

# Add the following lines to myApp/public/javascripts/application.js
//= require jquery
//= require jquery_ujs
//= require bootstrap
//= require_tree . 

# Round one done!

# Now repeat the following as you add and improve your new web site

# Get updates from collaborators
git pull 

# Continue to add objects, attributes, views (html, css, etc)
# Syntax is: rails generate migration AddXXXToYYYs attr1:<type>
# Adds a new attribute named attr1 to the object named yyy
# Types include: string, text, datetime, date, integer, binary,
#    boolean, float, decimal (for financial data), time, and timestamp
# Example: Add a string attribute named str2, a text attribute named
# text2, and a boolean attribute named bool2 to obj2
rails generate migration AddStuffToObj2s str2:string text2:text bool2:boolean

# Repeat as desired for new objects and attributes

# Apply new changes to the database after each change
rake db:migrate

# Commit changes often
# Helps if you need to go back to a prior version
git commit
git push 

# For collaborator's, they first need to create their
# own github account, then you can add them from the repo 
# settings page.

# They make their own local git repo for the project like this
git clone https://github.com/brucelhill/devImpact1


# Here's a better git repo strategy
# 1. Create a new github repo that will hold all the test
#	websites we create, so we don't have to keep creating
#	and sharing new repos.  I'm naming mine bh_repo1.
#
# 2. Checkout the new repo like this
C:\Sites>cd c:\

C:\>mkdir git-repos

C:\>cd git-repos

C:\git-repos>git clone https://github.com/brucelhill/bh_repo1
Cloning into 'bh_repo1'...
remote: Counting objects: 4, done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0)
Unpacking objects: 100% (4/4), done.

C:\git-repos>

# 3. 
