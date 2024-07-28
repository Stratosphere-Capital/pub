name = ansible

.PHONY: help hosts

hosts:
	echo [stratosphere] > hosts
	echo [stratosphere] > hosts_local
	cd host_vars; for dir in *; do echo "$$dir ansible_become=yes ansible_become_user=root"; done \
	    | grep -v example.stratosphere.capital >> ../hosts
	cd host_vars; for dir in *; do echo "$$dir ansible_become=yes ansible_become_user=root ansible_connection=local"; done \
	    | grep -v example.stratosphere.capital >> ../hosts_local

help:
	@echo "Usage:"
	@echo "    hosts      rebuild 'hosts' and 'hosts_local' according to host_vars contents"
