# CSC 395 - Fundamentals of Modern Linux Administration

## Lab Exercises

This repository is the starting point for all of the labs outlined in the primary
[course repository](https://github.com/draevin/csc395-linux) and is intended to be
forked for use by participants in the class. As you work through the exercises, update
this repository with your changes. When you need to turn in an assignment, create
a tag representing the weekly exercise that state represents.

## Starting contents

The initial contents of this repository include...

### `inventory` directory

When using Ansible, you must have an inventory defined. There are many ways to do
this depending on your use case, but for these exercises we will be using a directory
within the repository so that the information is kept in a single, centralized location.
To do this without additional overhead when running commands, we need to specify
that we're doing so in our `ansible.cfg` file (see below)

#### host_vars\az-workstation

##### main.yml

This is our primary host variable file. It contains a variety of variables specific
to the machine from which we will set up our Azure lab VMs. It comes with appropriate
defaults for this process.

##### `vault.yml` (REQUIRED -- NOT INCLUDED)

To configure your Azure lab VMs, you will need to provide a `vault.yml` file in this
directory with contents as follows:

```yaml
---
vault_admin_un: { yourUsernameHere-noBrackets }
vault_admin_pw: { yourPasswordHere-noBrackets }
```

### `ansible.cfg`

Ansible can be configured with various configuration files that change in scope
depending on location. The most specific file available is one in the current directory
when running commands. This config is provided with some appropriate defaults for
our lab needs. Further details on configuration and scope can be found in the official
docs section on [Ansible Configuration settings](https://docs.ansible.com/ansible/latest/reference_appendices/config.html)
