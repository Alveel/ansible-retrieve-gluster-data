# How to

Before you begin, I assume you know how [ansible](https://docs.ansible.com/ansible/latest/) and python virtual environments work.

1. Copy hosts.sample and edit it as necessary
1. Have a virtualenv active for this. I use [pyenv](https://github.com/pyenv/pyenv).
1. `pip install -r requirements.txt`
1. Have `oc` client installed
1. `heketi` binary must be copied to its volume (aka `/usr/bin/heketi` to `/var/lib/heketi`)
   * This must be done with Heketi still running
   * The playbook works regardless if Heketi is running or not, however
1. Be logged into the cluster you want
1. `ansible-playbook get-information.yaml`
1. When done, check the `retrieved-data` directory
1. Create archive and send to Red Hat: `XZ_OPT=0 tar -cJvf retrieved-data.$(date +%Y%m%d%H%M).tar.xz retrieved-data/$(date +%Y%m%d%H).*`

