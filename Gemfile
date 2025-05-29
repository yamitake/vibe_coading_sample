source "https://rubygems.org"

ruby "3.3.7"

gem "rails", "~> 7.1.3", ">= 7.1.3.2"
gem "sprockets-rails"
gem "puma", ">= 5.0"
gem "tailwindcss-rails"
gem "jbuilder"
gem "tzinfo-data", platforms: %i[ windows jruby ]
gem "bootsnap", require: false

# ✅ Use Slim as template engine
gem "slim-rails"

# ✅ Use Vite for frontend bundling (JavaScript/CSS)
gem "vite_rails"

group :development, :test do
  # Debugging tools
  gem "debug", platforms: %i[ mri windows ]
end

group :development do
  gem "web-console"

  # ✅ Enable automatic browser reloading (no Chrome extension needed)
  gem "rack-livereload"                 # Injects LiveReload script into HTML in development
  gem "guard"                           # File watching utility
  gem "guard-livereload", require: false # Sends reload events to the browser

  # ✅ Use Foreman for managing multiple processes via bin/dev
  gem "foreman"                         # Supports Procfile.dev for unified startup
end
