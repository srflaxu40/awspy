# awspy

tag_aws.py - tag services with a set of tags defined in an INI file (aws.ini) by vpc.

## Development Setup
* Mac OSX operating systems come with system-wide python - do not fuck with it.
* You don't have to install pyenv, but this was created using python v2.7.10.
* [Install PyEnv](https://github.com/pyenv/pyenv)
* [Install Homebrew](https://brew.sh/)
* `pip install virtualenv`
* `source awspy/bin/activate`
  * The above command should put you into the awspy project along with pre-installed modules.
  * If you do not install virtualenv, you'll have to install boto manually:
    `pip install boto`
    `pip install boto3`
    `pip install configparser`

## Running (only requires python)
* Have a looksy inside the aws.ini file to see a set of tags.  You can tag thingz with up to 50 tags maximum.
* `./tag_aws -v vpc-122303f`
