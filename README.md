# Setup

Create a new project
'''rails g your-project-name'''

Include navel_gazer in the Gemfile
  gem 'let_me_in', :git => 'git@github.com:becarella/let_me_in.git'
  gem 'navel_gazer', :git => 'git@github.com:becarella/navel_gazer.git'

Register api keys for:
* Banters (optional) https://banters.com/api/apps
* Twitter (optional) https://dev.twitter.com/apps
* Instagram (optional) http://instagr.am/developer/
* Embedly (required) http://embed.ly/docs

Store the keys in environment variables. On localhost, edit .bash_profile:
'''
  export BANTERS_KEY="xyz"
  export BANTERS_SECRET="abc"
  export TWITTER_KEY="xyz"
  export TWITTER_SECRET="abc"
  export INSTAGRAM_KEY="xyz"
  export INSTAGRAM_SECRET="abc"
  export EMBEDLY_KEY="whatevs"
'''

To host on heroku, register a new application and install the keys. https://devcenter.heroku.com/articles/config-vars
'''
  heroku config:add BANTERS_KEY=xyz
  ...
'''

Install the database migrations into your projects:
  rake let_me_in_engine:install:migrations
  rake navel_gazer_engine:install:migrations
  rake db:migrate
  
Add these routes to routes.rb
  root :to => 'navel_gazer/posts#index'
  match 'posts' => 'navel_gazer/posts#index'
  match 'signin' => 'let_me_in/sessions#new'
  match 'signout' => 'let_me_in/sessions#destroy'
  match 'auth/:provider/connect' => "let_me_in/auth#connect"
  match 'auth/:provider/disconnect' => 'let_me_in/auth#disconnect'
  match 'auth/:provider/callback' => 'let_me_in/auth#callback'
  match 'auth(/:provider)/failure' => 'let_me_in/auth#failure'
  match 'accounts' => 'let_me_in/linked_accounts#index'