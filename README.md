# Cell Profiling website

This is the source for the [Cell Profiling](https://cellprofiling.github.io/) website.

Please point your Pull Request (PR) at the `source` branch. After a PR has been merged with the source branch, a collaborator with push access can pull changes for source branch from the repo, then build locally and deploy to master branch at the repo. See below for commands.

## Git: Add changes in a new branch

| Command | Action |
|---|---|
| `git pull origin source` | pull changes in source branch from github to local |
| `git checkout -b pr-branch source` | create a new branch for a PR from source branch |
| `git push origin pr-branch` | push new commits of pr-branch to github |

## Github: Make the PR, review changes and merge into source branch

https://help.github.com/articles/using-pull-requests/

## Git: Pull changes to prepare for deploy

| Command | Action |
|---|---|
| `git pull origin source` | pull changes in source branch from github to local

## Octopress to generate and deploy

| Command | Action |
|---|---|
| `jekyll serve` | Preview site on [http://127.0.0.1:4000](http://127.0.0.1:4000)
| `jekyll build` | Generate new version of the site
| `octopress deploy` | Deploy a new version of the site

See the doc at [Octopress](https://github.com/octopress/octopress) for more information.

## Setup

_You need to have Ruby installed._

- [Ruby installation instructions](https://www.ruby-lang.org/en/documentation/installation/)

```bash
$ git clone https://github.com/CellProfiling/CellProfiling.github.io.git
$ cd CellProfiling.github.io
$ bundle
```

## Create a new blog post

```bash
$ octopress new post "My Title"
```

## Site preview

```bash
$ jekyll serve
```

The preview is now available on [http://127.0.0.1:4000](http://127.0.0.1:4000).

## Steps for the deployment of the site

All developers with write access to the repositories are able to deploy the website. The deploy process is fully automated with `jekyll build && octopress deploy`.

```
$ git pull origin source
$ jekyll build && octopress deploy
```

### Setup rvm and ruby

```bash
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
$ \curl -sSL https://get.rvm.io | bash -s stable
$ source ~/.profile
$ rvm requirements
$ rvm install ruby-2.2.1
$ rvm use ruby-2.2.1 --default
$ ruby -v
```

Then install `bundler`.

```bash
$ gem install bundler
```

Now please follow the Setup instructions above.
