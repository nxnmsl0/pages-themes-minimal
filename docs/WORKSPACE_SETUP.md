# Development workspace setup

This repository is the Minimal Jekyll theme for GitHub Pages. The workspace uses the repository's existing Ruby/Bundler setup and scripts to install dependencies, build the theme, and preview it locally.

## Tools and dependencies

- **Ruby 3.1** in the included VS Code Dev Container. The historical Travis configuration used Ruby 2.2; the container uses a newer runtime for a practical current development environment.
- **RubyGems and Bundler** to install and run the project's gems.
- **Jekyll** (`~> 3.5`) and **jekyll-seo-tag** (`~> 2.0`), as declared in `jekyll-theme-minimal.gemspec`.
- **Visual Studio Code** with the Ruby LSP and Markdown All in One extensions (automatically recommended/installed in the Dev Container).

The repository's `script/bootstrap` installs Bundler and runs `bundle install`. Its `script/cibuild` runs `bundle exec jekyll build` and builds the theme gem.

## Environment variables

No environment variables are required for installation, tests, or the local preview. The site's title, description, download link setting, and theme are configured in `_config.yml`. Add credentials or secrets only if a future workflow explicitly requires them; do not commit secrets to the repository.

## Start a workspace

### VS Code Dev Container

1. Open this repository in Visual Studio Code with the Dev Containers extension installed, or open it in a GitHub Codespace.
2. Choose **Reopen in Container** if prompted. The container runs `script/bootstrap` after creation.
3. Start the preview server in the integrated terminal:

   ```sh
   bundle exec jekyll serve --host 0.0.0.0
   ```

4. Open the forwarded port **4000** to view the site.

### Local machine

Install Ruby and RubyGems, then from the repository root run:

```sh
bash script/bootstrap
bundle exec jekyll serve
```

Open <http://localhost:4000> to preview the site.

## Build and verify changes

Run the repository's CI build locally:

```sh
script/cibuild
```

This builds the Jekyll site and the `jekyll-theme-minimal` gem. Build output is generated locally and should not be committed unless a change specifically calls for it.

## Editor conventions

The workspace recommends Ruby LSP and Markdown All in One. VS Code is configured to insert a final newline, trim trailing whitespace, and use two-space indentation for Ruby and YAML. Follow existing formatting in files where a project-specific convention is already established.
