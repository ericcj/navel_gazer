# for missing encoding in ancient httpauth gem (transitive dependency)
if RUBY_VERSION =~ /1.9/
  Encoding.default_external = Encoding::UTF_8
  Encoding.default_internal = Encoding::UTF_8
end

source "http://rubygems.org"

# Declare your gem's dependencies in navel_gazer.gemspec.
# Bundler will treat runtime dependencies like base dependencies, and
# development dependencies will be added by default to the :development group.
gemspec

gem 'pg'

# jquery-rails is used by the dummy application
gem "jquery-rails"

# Declare any dependencies that are still in development here instead of in
# your gemspec. These might include edge Rails or gems from your path or
# Git. Remember to move these dependencies to your gemspec before releasing
# your gem to rubygems.org.

gem 'omniauth-identity'
gem 'omniauth-instagram'
gem 'omniauth-twitter', '0.0.8'
gem 'omniauth-banters', :git => "git://github.com/becarella/omniauth-banters.git"
gem 'omniauth-foursquare'
gem 'omniauth-tumblr'
gem 'omniauth-lastfm'

#gem 'let_me_in', :git => 'git@github.com:becarella/let_me_in.git'
gem 'let_me_in', :git => 'git://github.com/becarella/let_me_in.git'
gem 'render_or_redirect', :git => 'git@github.com:becarella/render_or_redirect.git'

gem 'handlebars_wax', :git => 'git@github.com:goggin13/handlebars_wax.git'
gem 'handlebars_assets', :git => 'git@github.com:goggin13/handlebars_assets.git'

group :assets do
  gem 'sass-rails',   '~> 3.1.4'
  gem 'coffee-rails', '~> 3.1.1'
  gem 'uglifier', '>= 1.0.3'
end


# To use debugger
# gem 'ruby-debug19', :require => 'ruby-debug'
