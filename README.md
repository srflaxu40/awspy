# awspy

tag_aws - tag services with a set of tags defined in an INI file (aws.ini) by vpc.

@TO-DO - allow specifying the service section in the INI ex - ec2, rds, elasticache, etc.
@TO-DO - cleanup/tag deletion?  maybe..

## Development Setup
* Mac OSX operating systems come with system-wide python - do not fuck with it.
* Setup [aws credentials](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)
* You don't have to install pyenv, but this was created using python v2.7.10.
* [Install PyEnv](https://github.com/pyenv/pyenv)
* `pip install virtualenv`
* `source awspy/bin/activate`
  * The above command should put you into the awspy project along with pre-installed modules.
  * If you do not install virtualenv, you'll have to install the modules manually:
    - `pip install boto`
    - `pip install boto3`
    - `pip install configparser`

## Running (only requires python)
* This script uses boto, which wraps the AWS SDK.  This requires setting up your [AWS credentials configuration](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)
* Have a looksy inside the aws.ini file to see a set of tags.  You can tag thingz with up to 50 tags maximum.
* `./tag_aws -v vpc-122303f`
* Dry run:
  - `./tag_aws -v vpc-122303f -d`
