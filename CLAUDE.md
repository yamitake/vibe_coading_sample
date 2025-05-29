# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

Start the development server with live reloading:
```bash
bin/dev
```
This runs Rails server, Vite dev server, and Guard for live reloading simultaneously.

Individual service commands:
```bash
bin/rails server        # Rails app server
bin/vite dev            # Vite frontend dev server  
bundle exec guard       # File watcher for live reloading
```

Rails commands:
```bash
bin/rails console       # Rails console
bin/rails generate      # Code generators
bin/rails routes        # View all routes
```

## Architecture Overview

This is a Rails 7.1 application with a modern frontend setup:

**Backend**: Rails API-style setup with no ActiveRecord/database (ActiveRecord railtie is commented out in application.rb). Uses ActionController, ActionView, and ActionCable.

**Frontend**: Vite.js for asset bundling with vite-plugin-ruby integration. Frontend code lives in `app/frontend/` with entrypoints and styles directories.

**Template Engine**: Slim templates (see Gemfile and views using .slim extension)

**Styling**: TailwindCSS configured via tailwindcss-rails gem

**Live Reloading**: Full browser refresh setup using Guard + LiveReload + rack-livereload for immediate feedback during development

**Process Management**: Foreman with Procfile.dev orchestrates the Rails server, Vite dev server, and Guard file watcher

## Key Configuration Files

- `vite.config.ts`: Vite configuration with Ruby plugin
- `Guardfile`: File watching patterns for live reloading (watches views, helpers, assets, locales)
- `Procfile.dev`: Development process definitions for bin/dev
- `config/application.rb`: Rails configuration with database disabled