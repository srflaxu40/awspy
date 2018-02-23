# awspy

* Notes:
  * Be sure to set the correct profile through `export AWS_PROFILE=<some profile in ~/.aws/credentials>`

---

- @TO-DO - allow specifying the service section in the INI ex - ec2, rds, elasticache, etc, as a CML option (ie. only tag this service).
- @TO-DO - cleanup/tag deletion?  maybe..

## Development Setup
* Mac OSX operating systems come with system-wide python - do not fuck with it.
* Setup [aws credentials](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)
* If you have pyenv-virtualenv installed for python, feel free to activate the virtual env:
`pyenv activate awspy`
* `pip install -r requirements.txt`

## Running (only requires python)

### tag_aws
* Have a looksy inside the aws.ini file to see a set of tags.  You can tag thingz with up to 50 tags maximum.
* Dry run:
  - `./tag_aws -v vpc-122303f -d`
* Run:
  - `./tag_aws -v vpc-122303f`

### clean snaps:
* Dry run:
  - `./clean --snaps 'jenkins-ebs-snapshot-*' --keep 10 -d`
* Run:
  - `./clean --snaps 'jenkins-ebs-snapshot-*' --keep 10`

### clean amis:
* Dry run:
  - `./clean --amis 'kube_slave*' --keep 10 -d`
* Run:
  - `./clean --amis 'kube_slave*' --keep 10`

### IAM Key Deactivation:
* This script goes through users in IAM, deletes their keys forcing them to log in and create new ones.
* This requires users have MFA auth enabled.  This can be checked in the UI.  MFA is how individual user
  accounts are distinguished versus service accounts used for applications, etc, that you would not want to delete (AWS Keys).
* First ensure you have the right *AWS_PROFILE* set.  These are located in the `~/.aws/credentials` file.  In this case, I 
  am going to use the default account:

```
export AWS_PROFILE=default
```

* Run:
  - `./rotate` # Follow prompt...

* To delete an individual user's keys:
  - `./rotate --user=johndoe`

* To list users:
  - `./rotate --list`
