# Hackathon website template

This is a template repository for a public-facing hackathon website, built by the [Jean Golding Institute](https://www.bristol.ac.uk/golding/) at the University of Bristol.

The template is designed to get you started as quickly as possible with a working website. For this reason we have built a [GitHub Pages](https://pages.github.com/) website so you can also host it for free and allow others to collaborate easily.

Most of the pages have been written to require only minor editing, however you have the flexibility to completely change them or add new pages as required.

Demo: <https://jean-golding-institute.github.io/hackathon-template>

## Getting started

### GitHub pages

[GitHub Pages](https://docs.github.com/en/pages) allows you to create a website using a GitHub-customised version of the static site generator [Jekyll](https://jekyllrb.com/).

1. Fork this repository in GitHub
   * If you have a GitHub organisation for the event and want this to be it's primary website, name your new repository: `your-organisation-name.github.io`
2. Under your new repository settings, go to `Settings` > `Pages`
   * Switch GitHub pages on
   * Ensure the `Source` is set to the `main` branch and `/ (root)` directory
   * **Don't** adjust the theme, this is set in `_config.yml`

### Local development

Although you can do all you development via the GitHub website, it is recommended that you clone your GitHub repository locally. This will allow you to test your changes locally in a web browser before committing them.

Jekyll requires [Ruby](https://www.ruby-lang.org) in order to run. It uses a file called `Gemfile` to define which Ruby libraries are required. We have already taken some necessary setup steps, including creating the Jekyll site and the associated `Gemfile` and `Gemfile.lock` files.

The GitHub Pages docs contain [detailed instructions on testing you site locally](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) using different operating systems, however in summary the process is:

1. (On Windows) [Install Git Bash](https://gitforwindows.org/) if you don't have it already
   * It is recommended you run the rest of these commands from within a Git Bash window
2. Clone the GitHub repository to a local Git repository
   * Run the command: `git clone https://github.com/your-organisation/your-repository.git`
   * Or: `git clone git@github.com:your-organisation/your-repository.git`
3. Install Ruby
   * Check if it's already installed by running the command `ruby -v`
   * Follow the [Ruby installation docs](https://www.ruby-lang.org/en/documentation/installation/) for your operating system if it isn't
4. Install Bundler
   * `cd` to your repository's root directory if you're not there already
   * Run the command: `gem install bundler`
   * This tool will assist in the next step with installing the Ruby libraries specified in the `Gemfile`
   * See the [Bundler website](https://bundler.io/) for more information
5. Install Jekyll and other required Ruby libraries
   * `cd` to your repository's root directory if you're not there already
   * Run the command: `bundle install`
6. Run a local web server to test your site
   * `cd` to your repository's root directory if you're not there already
   * Run the command: `bundle exec jekyll serve`
   * Then visit: <http://127.0.0.1:4000/>
   * Or, if you are hosting the website in a subdirectory then you can run `bundle exec jekyll serve -b /subdirectory-name-here` and then visit <http://127.0.0.1:4000/subdirectory-name-here/>

All together, that's:

```bash
$ git clone https://github.com/your-organisation/your-repository.git
$ cd your-repository
$ gem install bundler
$ bundle install
$ bundle exec jekyll serve -b /your-repository
```

### Editing the website

A Jekyll website is a collection of Markdown pages and a set of templates used to render them into HTML files. The pages are written using the [Kramdown](https://kramdown.gettalong.org/quickref.html) flavour of Markdown and the templates are written in [Liquid](https://shopify.github.io/liquid/) template language with [some Jekyll additions](https://jekyllrb.com/docs/liquid/).

With the default GitHub pages setup (where GitHub will render you site for you when you push changes to your repository), you are limited to Jekyll version 3.9.0 and a [subset of Jekyll plugins](https://pages.github.com/versions/) (you can't add your own).

We have tried to put as many of the common site settings and variables in `_config.yml`, which is the configuration file used by Jekyll. Note that when developing locally, if you change the `_config.yml` then you will need to restart the local web server (the command `bundle exec jekyll serve`) because this change will not be automatically detected.

#### Things to change in `_config.yml`

* `title`: The name of the site used in the title bar and various other places

* `nav_title`: The name and strapline of the site used in the top nav, with optional `<span>` tags allowing for parts of it to be hidden when viewing on a mobile phone

* `event_date`: The date(s) of your event, displayed in various places around the site

* `registration_opens_date`: As above, but the date registration opens (this doesn't control when the form is actually diaplayed – see below for how to do this)

* `registration_closes_date`: As above, but the date registration closes

* `author`: The organising institution

* `mailbox_address`: An email address for correspondence (recommended to be a shared mailbox)

* `description`: A short event description, visible to search engines and on social media previews

* `url`: The address of your published site (without the trailing slash)

* `github_repo`: The name of your GitHub organisation (or site repository, if you prefer)

As the event organisation progresses, you will want to show different content on your site:

* `event_status`: Controls which pages are displayed, depending on whether the event is in the future, happening now, or was in the past (by default, the pages affected by this setting are `Index` (the homepage), `Registration`, `Agenda` and `Videos & slides`)

* `registration_status`: Controls whether the link to your registration for is displayed

#### Other things to change

* The content of the individual pages (`index.md`, `agenda.md`, for example), as not everything will be covered by the configuration file

* `assets/logo.png`: The logo displayed on the top nav bar

* `assets/advert.png`: The image displayed on social media when people share the site

* If you want to add extra pages to the nav bar, then change `header_pages` in `_config.yml`
  * Set `menu_title` and `menu_icon` in the [front matter](https://jekyllrb.com/docs/front-matter/) of the page
  * You can additionally control page visibility using `event_status`
  * Icons are the [Bootstrap Icons](https://icons.getbootstrap.com/)

#### Editing tips

* Use [Liquid variables](https://jekyllrb.com/docs/variables/) to refer to variables set in `_config.yml` or the [front matter](https://jekyllrb.com/docs/front-matter/) of a page, for example:

      {{ site.event_date }}

* Use the [Liquid link tag](https://jekyllrb.com/docs/liquid/tags/#links) to link to other pages using their Markdown filename, for example:

      [Link to code of conduct]({{ site.baseurl }}{% link code-of-conduct.md %})

  The link will be automatically rendered to the correct HTML file. Always start links from the root of the site, and because this is Jekyll 3.9 (rather than 4), you need to prepend the link with `{{ site.baseurl }}`

### Publish your changes

After committing your changes, push the `main` branch back to GitHub, and the site will be built automatically. This may take a few minutes and you may need to force refresh the page in your web browser to see changes.

For example:

```bash
$ git add .
$ git commit -m "Add agenda to website"
$ git push
```

## Contributors

* [James Thomas](https://github.com/jatonline), Jean Golding Institute

## Acknowledgements

This template was originally based on the [CMIP6 Data Hackathon](https://cmip6moap.github.io/) website and resources that we created for the event on 2–4 June 2021. It has now been modified to suit a wider variety of virtual hackathons.
