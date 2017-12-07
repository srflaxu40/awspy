# awspy

tag_aws - tag services with a set of tags defined in an INI file by vpc.
* The file must be in INI format.
* See aws.ini for the structure:
```
[elasticache]
name=test
some=tag
[ec2]
name=test2
over=rainbow
another=test
[rds]
name=test3
tag=myrds
```

* Now run (see "Running" for additional opts):

  `./tag_aws -v vpc-122303f`

---

- @TO-DO - allow specifying the service section in the INI ex - ec2, rds, elasticache, etc, as a CML option (ie. only tag this service).
- @TO-DO - cleanup/tag deletion?  maybe..

## Development Setup
* Mac OSX operating systems come with system-wide python - do not fuck with it.
* Setup [aws credentials](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)
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
