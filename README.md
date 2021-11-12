api-task
========
### Prerequisites
    Ruby - 2.7.3
    Bundler - 2+
    Postgres

### Setup
- git clone git@github.com:vitalyp/api-task.git
- bundle install
- RACK_ENV=test bundle exec rake db:create db:migrate
- RACK_ENV=development bundle exec rake db:create db:migrate database:reset

### Rake database tasks (RACK_ENV=development/test)

    database:reset - Drops database and recreates initial database structure
    database:load  - Load database with amount of data
       
### Checks

- bundle exec rspec spec
- bundle exec rubocop

### Setup

    RACK_ENV=development bundle exec rake db:create
    RACK_ENV=test bundle exec rake db:create

### Run server
With live reload:
    
    shotgun
    
Standard:
    
    rackup

### Endpoints

Create post:

    curl -i -X POST -H "Content-Type: application/json" -d'{"title":"Post title","content":"Post content","login":"user1","ip":"127.0.0.1"}' http://127.0.0.1:9393/posts 
