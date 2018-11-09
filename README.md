# A sample example of test kitchen plugin kitchen-terraform for testing Terraform configurations

## The purpose of this repo is to demonstrate usage of kitchen-terraform plugin of test kitchen to test Terraform configuration

### Prerequisites

* git
* terraform
* AWS subscription
* AWS SSH key apir for your linux user

### Requirements

* ruby  (2.3.1)
* test-kitchen (~> 1.21.2)
* kitchen-terraform (~> 3.3.1)

## How to use

### Download the repo and go to the repo directory

```
git clone https://github.com/achuchulev/ec2-kitchen-terraform.git
cd ec2-kitchen-terraform/
```

### Create a terraform.tfvars file and reflect your setup there

```
access_key = ""
secret_key = ""
key_name = ""
region = ""
ami = ""
instance_type = ""
```

### Export your AWS access key and secret key as enviroment variables

```
export AWS_ACCESS_KEY_ID=
export AWS_SECRET_ACCESS_KEY=
```

## How to test

### on Linux

##### Install bundler

```
sudo gem install bundler
bundle install
```

#### Run test

Run command: 

```
bundle exec kitchen test
```

### on MAC

#### Prerequisites

##### Install rbenv to use ruby version 2.3.1

```
brew install rbenv
rbenv install 2.3.1
rbenv local 2.3.1
rbenv versions
```

##### Add the following lines to your ~/.bash_profile:

```
eval "$(rbenv init -)"
true
export PATH="$HOME/.rbenv/bin:$PATH"
```

##### Reload profile: 

`source ~/.bash_profile`

##### Install bundler

```
gem install bundler
bundle install
```

#### Run the test: 

`bundle exec kitchen test`

#### Tree view of directory structure

```
.
├── Gemfile
├── LICENSE
├── README.md
├── main.tf
├── outputs.tf
├── terraform.tfvars
├── test
│   └── integration
│       └── default
│           ├── controls
│           │   └── operating_system_spec.rb
│           └── inspec.yml
└── variables.tf
```
