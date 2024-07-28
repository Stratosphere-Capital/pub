ANSIBLE
=======

There is a `common` role with setup for all servers.

There are specialized roles to setup common dockerized services.

There is only a single playbook for every server.  All are defined in `playbooks.yml`.


common
++++++

- UTC timezone
- user accouts with ssh keys
- sshd_config
- zsh and bash defaults
- postfix MTA setup - to be able to send emails
- ansible-local - run ansible faster through `ansible-local`


docker-service
++++++++++++++

- a generic docker service deployable through `stctl deploy`


USAGE
=====

Deploy to all servers:::

    ansible-playbook playbooks.yml -i hosts -u <your-username>

You can specify a subset of servers by `-l`. If you want to run just a specific
tag, add `-t <tag-name>`.  For the list of available tags, see `playbooks.yml`.

Deploy locally:::

    ansible-local

on the server where you want to deploy.
