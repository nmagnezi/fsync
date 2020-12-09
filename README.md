CodeSync
========

CodeSync will Sync your git folders to or from a local directory and a 
remote machine.

## How To Install
    pip install codesync

## Options

##### positional arguments:
      -p PROJECT, --project PROJECT
                            The name of your git project, stored under your
                            local/remote path.

      -d {to,from}, --direction {to,from}
                            Sync Direction
    
      -i IP, --ip IP        IP Address or FQDN for SSH connection


##### optional arguments:
      -r REMOTE, --remote REMOTE
                            Remote git folder. Default: ~/git

      -l LOCAL, --local LOCAL
                            Local git folder. Default: ~/git
    
      -u USER, --user USER  Username for ssh connection. Default: stack

      -e [EXCLUDE [EXCLUDE ...]], --exclude [EXCLUDE [EXCLUDE ...]]
                            Exclude list for rsync. Default: ['.tox', '.idea',
                            '.pyc', '.pyo', '.swp', '.swo', '.git', '.iml',
                            'target', 'build', '__pycache__']

## Usage Example

    codesync -p myproject -d from -i 10.35.6.107 -u nmagnezi -r /Users/nmagnezi/git -l ~/git -e .git .tox

## How does it work?

These are steps performed by CodeSync:

1. Validate your node has rsync installed.
2. Use rsync to sync the delta between source and destination.
