# Spin up a docker swarm cluster

Used for fast deployment of a test swarm for testing different cluster failover scenarios mainly with Docker Enterprise.

# Known issues

## --retry don't work

Because we need to get the swarm join token from ucp. If `--retry` excludes ucp node then an error will be joining worker nodes into the swarm.

# Resources

* https://github.com/nextrevision/ansible-swarm-playbook
