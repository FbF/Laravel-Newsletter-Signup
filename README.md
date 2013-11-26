Laravel Newsletter Signup
=========================

A Laravel 4 Package for adding newsletter signup (and unsubscribe) functionality to a web site

## Features

* Partials for a signup and an unsubscribe form, that you can include in your own views
* Controller actions to handle the submissions of the forms, which can handle normal (redirects to previous page), or AJAX requests (responds with JSON with status code and message)
* Translation approach for customising labels, buttons, feedback messages and validation errors
* Currently only supports saving to a database through a supplied Eloquent model (migration included), but will hopefully be extended to support mailing list API services in future
* Includes a FrozenNode/Laravel-Administrator config file with Download Signups CSV and Download Unsubscribes CSV buttons
* Twitter bootstrap compatible markup and class names for the forms

## Installation

Add the following to you composer.json file

    "fbf/laravel-newsletter-signup": "dev-master"

Run

    composer update

Add the following to app/config/app.php

    'Fbf\LaravelNewsletterSignup\LaravelNewsletterSignupServiceProvider'

Publish the config

    php artisan config:publish fbf/laravel-newsletter-signup

Run the migration

    php artisan migrate --package="fbf/laravel-newsletter-signup"

Optionally copy the administrator config to your administrators model config directory, if you have one

## Configuration

Coming soon

## Usage

There is a route and a view supplied for rendering both the signup and unsubscribe forms, and you can configure the actual view and the actual uri in the config file.

However, you will most likely want to just @include one of the partials somewhere in your existing views, for example:

	@include('laravel-newsletter-signup::signup')

or

	@include('laravel-newsletter-signup::unsubscribe')

This will render the sign up or the unsubscribe form.

## Administrator

You can use the excellent Laravel Administrator package by frozennode to view and download your signups and unsubscribes.

http://administrator.frozennode.com/docs/installation

A ready-to-use model config file for the Signup model (newsletter.php) is provided in the src/config/administrator directory of the package