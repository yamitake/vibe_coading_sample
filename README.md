# Vibe Coding Sample

A modern Rails 7.1 application with Vite.js frontend bundling, live reloading, and no database dependencies.

## Architecture

- **Backend**: Rails 7.1 with ActionController, ActionView, and ActionCable (no ActiveRecord/database)
- **Frontend**: Vite.js for asset bundling with vite-plugin-ruby integration
- **Templates**: Slim template engine
- **Styling**: TailwindCSS via tailwindcss-rails gem
- **Live Reloading**: Guard + LiveReload + rack-livereload for instant feedback
- **Process Management**: Foreman orchestrates development services

## Prerequisites

- Ruby 3.x
- Node.js 18+ and npm
- Bundler gem

## Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd vibe_coading_sample
   ```

2. **Install dependencies**
   ```bash
   bundle install
   npm install
   ```

3. **Setup the application** (if bin/setup exists)
   ```bash
   bin/setup
   ```

## Development

### Quick Start
Start all development services with live reloading:
```bash
bin/dev
```

This runs:
- Rails server (port 3000)
- Vite dev server (for frontend assets)
- Guard file watcher (for live reloading)

### Individual Services
Run services separately if needed:
```bash
bin/rails server        # Rails app server
bin/vite dev            # Vite frontend dev server  
bundle exec guard       # File watcher for live reloading
```

### Common Rails Commands
```bash
bin/rails console       # Rails console
bin/rails generate      # Code generators
bin/rails routes        # View all routes
```

## Project Structure

```
app/
├── frontend/           # Frontend assets (Vite)
│   ├── entrypoints/   # JavaScript entry points
│   └── styles/        # CSS/SCSS files
├── controllers/       # Rails controllers
├── views/            # Slim templates
└── assets/           # Traditional Rails assets

config/
├── vite.json         # Vite configuration
└── ...               # Rails configuration

Guardfile             # Live reload configuration
Procfile.dev          # Development process definitions
vite.config.ts        # Vite bundler configuration
```

## Key Features

- **No Database**: Application runs without ActiveRecord or database dependencies
- **Live Reloading**: Changes to views, helpers, assets, and locales trigger automatic browser refresh
- **Modern Frontend**: Vite.js provides fast asset bundling and hot module replacement
- **Slim Templates**: Cleaner, more readable template syntax
- **TailwindCSS**: Utility-first CSS framework for rapid styling

## Development Workflow

1. Start development server: `bin/dev`
2. Edit files in `app/` directory
3. Browser automatically refreshes on file changes
4. Frontend assets are bundled by Vite in real-time

## Configuration Files

- `vite.config.ts`: Vite configuration with Ruby plugin
- `Guardfile`: File watching patterns for live reloading
- `Procfile.dev`: Development process orchestration
- `config/application.rb`: Rails configuration (database disabled)