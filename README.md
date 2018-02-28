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

## I just want to try it out
Assuming you have went through the instructions on [aws-dev-env-template](https://github.com/lyang/aws-dev-env-template), and have all prerequisite setup.

```
git clone --recurse-submodules https://github.com/lyang/my-aws-dev-env.git
```
You need to make changes to [s3-backend-config](files/s3-backend-config) to use your own S3 bucket for terraform backend.

Then:
```
cd my-aws-dev-env.git && ansible-playbook provision.yml
```

You will be prompted to review the terraform execution plan and then ssh host key verification of the new EC2 instance. The setup shouldn't take more than a few minutes.

By now you should be able to `ssh dev` into your new instance and play around. If you have VNC client installed, you should be able to connect to `localhost:5901` leveraging SSH port forward.

## What's next?
If you find this useful, you can copy the structure of this project and tweak the setup to better suit your needs.
You can also clone or fork this repo, but I won't accept any pull requests as this repo is my personal setup.

However, if you think there's something missing or should be more customizable in the [aws-dev-env-template](https://github.com/lyang/aws-dev-env-template), feel free to create issues there. Or better yet, create pull requests so everyone can benefit. I'm happy to review and merge bug fixes and enhancement (if it's generic enough).
