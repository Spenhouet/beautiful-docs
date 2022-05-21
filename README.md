<p align="center">
  <a href="https://github.com/Spenhouet/beautiful-docs/actions?query=workflow%3ABuild+branch%3Amain"><img src="https://github.com/Spenhouet/beautiful-docs/workflows/Build/badge.svg?branch=main" alt="Build Status"></a>
  <a href="https://hub.docker.com/r/slatedocs/slate"><img src="https://img.shields.io/docker/v/slatedocs/slate?sort=semver" alt="Docker Version" /></a>
</p>

<p align="center">This is a beautifully themed version of the <a href="https://github.com/slatedocs/slate">slate docs</a>.</p>

<p align="center"><img src="https://raw.githubusercontent.com/Spenhouet/beautiful-docs/c642fa12587849f5d9cdb178d5eb8a0bb00c34ec/img/screenshot-beautiful-docs.png" width=700 alt="Screenshot of Example Documentation created with the beautiful-docs theme of Slate"></p>

<p align="center"><em>Check this design out at <a href="https://spenhouet.com/beautiful-docs/en/">spenhouet.com/beautiful-docs</a>.</em></p>

## Features

### On top of Slate

* **Internationalization (i18n) support** — These docs come with i18n fully set up. Just write your docs in what ever languages you want to support.

* **Space efficient** — If there is no code block on the right, this slate design expands the left section over the whole page to give more room to your important content.

* **Even more beautiful** — Sleek design and color theme.

* **Search with wildcards** — The search box also matches partial matches.

* **Subsection structure** — All content was structured in subsections.

* **Mobile optimized** — Some small issues were addressed. 

### Slate Base Features

* **Clean, intuitive design** — With Slate, the description of your API is on the left side of your documentation, and all the code examples are on the right side. Inspired by [Stripe's](https://stripe.com/docs/api) and [PayPal's](https://developer.paypal.com/webapps/developer/docs/api/) API docs. Slate is responsive, so it looks great on tablets, phones, and even in print.

* **Everything on a single page** — Gone are the days when your users had to search through a million pages to find what they wanted. Slate puts the entire documentation on a single page. We haven't sacrificed linkability, though. As you scroll, your browser's hash will update to the nearest header, so linking to a particular point in the documentation is still natural and easy.

* **Slate is just Markdown** — When you write docs with Slate, you're just writing Markdown, which makes it simple to edit and understand. Everything is written in Markdown — even the code samples are just Markdown code blocks.

* **Write code samples in multiple languages** — If your API has bindings in multiple programming languages, you can easily put in tabs to switch between them. In your document, you'll distinguish different languages by specifying the language name at the top of each code block, just like with GitHub Flavored Markdown.

* **Out-of-the-box syntax highlighting** for [over 100 languages](https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers), no configuration required.

* **Automatic, smoothly scrolling table of contents** on the far left of the page. As you scroll, it displays your current position in the document. It's fast, too. We're using Slate at TripIt to build documentation for our new API, where our table of contents has over 180 entries. We've made sure that the performance remains excellent, even for larger documents.

* **Let your users update your documentation for you** — By default, your Slate-generated documentation is hosted in a public GitHub repository. Not only does this mean you get free hosting for your docs with GitHub Pages, but it also makes it simple for other developers to make pull requests to your docs if they find typos or other problems. Of course, if you don't want to use GitHub, you're also welcome to host your docs elsewhere.

* **RTL Support** Full right-to-left layout for RTL languages such as Arabic, Persian (Farsi), Hebrew etc.

Getting started with Slate is super easy! Simply press the green "use this template" button above and follow the instructions below. Or, if you'd like to check out what Slate is capable of, take a look at the [sample docs](https://spenhouet.com/beautiful-docs/en/).

## Getting Started

Provided in the slate repo is a Dockerfile you can use to run slate using [Docker](https://www.docker.com/), as well as providing pre-built images on [Docker Hub](https://hub.docker.com/r/slatedocs/slate). Docker is similar to Vagrant in that it provides a reproducible, portable development environment using virtualization, however it does not provide a full VM, rather piggy backing off the host, allowing for a slimmer installation profile than Vagrant / full VMs. However, Docker does come with a number of its own terms, and for beginners, we recommend looking at
[this Glossary](https://docs.microsoft.com/en-us/dotnet/architecture/microservices/container-docker-introduction/docker-terminology)
to familiarize yourself with some of them.

### Dependencies

* [Docker](https://www.docker.com/), see [this page](https://www.docker.com/get-started) for installing Docker Desktop.

### Getting Started

1. Fork this repository on Github.
2. Clone *your forked repository* (not our original one) to your hard drive with `git clone https://github.com/YOURUSERNAME/beautiful-docs.git`
3. `cd beautiful-docs`
4. Grab the slate image (`docker pull slatedocs/slate`) or build the docker image for the repository (`docker build . -t slatedocs/slate`).

### Build your Docs

To use Docker to just build your site, run:

```
docker run --rm --name slate -v $(pwd):/srv/slate slatedocs/slate build
```

After this command completes, you should see the built artifacts for your site in the `$(pwd)/build` directory, which you can then statically serve for your website.

_Note_: You may omit the final `build` argument and get the same result. By default, if given no command, the Dockerfile will run `build`.

### Serve your Docs for Development

If you wish to run the development server for Slate to aid in working on the site, run:

```
docker run --rm --name slate -p 4567:4567 -v $(pwd):/srv/slate slatedocs/slate serve
```

and you will be able to access your site at http://localhost:4567 until you stop the running container process.

### Deploy your Docs to GitHub Pages

Publishing your API documentation couldn't be more simple.

Run `./deploy.sh --push-only` once. After that, GitHub actions should do the building and deployment for you.

Done! Your changes should now be live on http://yourusername.github.io/beautiful-docs. Note that it can take some minutes until your docs are deployed, especially if this is your first time.
