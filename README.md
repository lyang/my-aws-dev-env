# What is this

This is the automatic setup of my EC2 dev env after it's been bootstrapped by the template.

## What does it do

* Setup terraform S3 backend config in the submodule
* Run terraform plan
* Apply terraform after plan confirmation
* Insert a piece of ssh config in my `~/.ssh/config` so I can simply `ssh dev` into the new machine
* Install and config packages I use

## What can I use it for

Probably isn't very much useful to you with my personal specific setup, but it can serve as an example on how to use the [aws-dev-env-template](https://github.com/lyang/aws-dev-env-template) to setup your own.
