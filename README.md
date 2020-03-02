# Ryan Hunter Personal Website

This repo holds the source code for [Ryan Hunter's personal website](https://www.ryanhunter.us).

It is a Jekyll site, based on [jekyll-tailwind-starter](https://github.com/mhanberg/jekyll-tailwind-starter).

It uses [Jekyll](https://jekyllrb.com) with [Tailwind CSS](https://tailwindcss.com),
[Autoprefixer](https://github.com/postcss/autoprefixer),
and [Purgecss](https://github.com/FullHuman/purgecss) (only in production).

*NOTE: The starter pack included a `bin/setup` script which handled initializing a git repo and
initializing the Tailwind config. Since that isn't needed anymore, I removed that script.
I then renamed the `bin/bootstrap` (which bootstraps a new development environment) to `bin/setup`,
since that's what I normally expect a `setup` script to do.*

## Usage

```bash
# Setup a new development environment
git clone git@github.com:ryan-hunter-pc/rh-website.git
cd rh-website
bin/setup

# Start the server
bin/start

# Create a new post
bin/new My New Post
```

## File Structure

```
+---_includes
    \---analytics.html // place your analytics tracking snippet in here
    \---syntax.css // Syntax highlighting CSS
    \---tailwind.config.js // Tailwind configuration.
+---_layouts
    \---default.html
    \---page.html
    \---post.html
+---_posts
+---_bin
    \---setup // Install dependencies
    \---new // Create a new post and open it in your $EDITOR
    \---start // Start the server with the livereload, incremental, drafts, and future flags on port 5000
+---_css
    \---site.css // Entry point stylesheet. You can write your styles here or import them from the _includes directory
+---index.md // Front page. This can be changed to an HTML file if desired.
+---404.html 
+---_config.yml // Jekyll configuration
+---postcss.config.js // PostCSS configuration. All plugins should be registered here.
+---purgecss.config.js // Purgecss configuration 
+---netlify.toml // Netlify configuration 
```

## PostCSS plugins

- Tailwind CSS
- Autoprefixer
- postcss-import

## Deployment

This setup has been tested on [Netlify](https://www.netlify.com).
The JEKYLL_ENV environment variable must be set to production in order for PurgeCSS to execute.
The included netlify.toml file will configure this on Netlify deploys.
