# Spin up a docker swarm cluster using ansible

Used for fast deployment of a test swarm for testing different cluster failover scenarios mainly with Docker Enterprise.

# Architecture

* `shared-service`
  * DNS resolver
  * NFS server
* `ucp`
  * swarm node
* `worker`
  * swarm worker

# Limitations

* only one `shared-service` host
* only one swarm manager (you can promote nodes to manager after running the playbook)

# Usage

* edit `inventory.ini`
* edit `main.yml`
  * set ucp admin password in variable `ucp_password`
* run `ansible-playbook main.yml`
* login to your ucp-IP with user `admin` and password specified in the step above

# Known issues

## --retry don't work

Because we need to get the swarm join token from ucp. If `--retry` excludes ucp node then an error will be joining worker nodes into the swarm.

# Resources

* https://github.com/nextrevision/ansible-swarm-playbook
