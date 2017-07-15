# ansible-tutorial

Content and code for the Ansible workshop I conducted at SANOG 2017 in Gurgaon.

This tutorial is an attempt to explain Ansible to beginners by using practical
examples.

## Table of Contents

1. Setup
2. Example 1 - Hello World with `debug` module
  2.1 Understanding plays and playbooks
  2.2 Understanding the inventory file
  2.3 Understanding host grouping using inventory file
3. Understanding `roles`
  3.1 Example 2 - installing Java
  3.2 Example 3 - installing Elasticsearch
  3.3 Example 4 - installing the entire ELK stack
4. Understanding variables and configuring roles
  4.1 Example 5 - configuring the ELK stack with Nginx
  4.2 Example 6 - using facts to configure JVM for Elasticsearch
5. Writing your custom role
  5.1 Example 7 - write a role for Logstash forwarder

## Setup

### For Running/Executing Ansible

#### Operating System

Preferrably Mac OS or Linux.

**Note:** Windows users can also use this but will have to figure out the
relevant changes by themselves).

#### Requirements

* Python 2.7 (comes installed on almost all Linux distros and Mac OS)

Other Python dependencies:

* `virtualenv` - not a requirement but its good to have it so that you don't
  mess up your global Python environment. Its super useful.

  [A quick introduction to Virtualenv][1]

* `ansible`

  If you are using `virtualenv`, then activate your `virtualenv`.

  Install `ansible` like so:

  ```
  pip install ansible
  ```

  [pip][2] is the Python package manager.

[1]: https://www.dabapps.com/blog/introduction-to-pip-and-virtualenv-python/
[2]: https://packaging.python.org/tutorials/installing-packages/

## Tutorial

### The directory structure

You will usually keep your Ansible code (playbooks, variables, roles) in one
place. Occassionally, you will want to create separate repos for roles or
completely separate repos for a system. These things depend on what your
requirements are. You don't need to worry about them right now. You will know it
when you need to.

For now, lets get started by creating a new repository:

```
# Create a new directory at a path of your choosing
mkdir ansible-workshop
cd ansible-workshop

# Create an empty git repository so that you can commit your Ansible code
git init
```
