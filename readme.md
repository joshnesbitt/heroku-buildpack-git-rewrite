# Heroku Buildpack Git Rewrite


## Introduction

A Heroku buildpack for setting the ssh private key as part of the application build. It's meant to be used as part of a setup [using multiple buildpacks](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app), so other buildpacks can authenticate with hosts using ssh keys, for instance to install dependencies from private git repositories.


## Installation

Add the buildpack to your Heroku app either using the CLI or the Heroku dashboard. This buildpack needs to run before any other buildpacks make SSH calls (such as the `heroku/nodejs` buildpack performs an `npm install`):

    $ heroku buildpacks:set --index 1 https://github.com/joshnesbitt/heroku-buildpack-git-rewrite.git
    $ heroku buildpacks:add heroku/nodejs
