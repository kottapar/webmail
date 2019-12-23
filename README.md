# Webmail

Write an ansible playbook to create webmail front-end (i.e rainloop) docker image from ubuntu 19.10. Playbook should deploy podman image to the local registry. (Pleae create ansible role for creating local registry )

Create helm chart for deploying webmail front-end image to a kubernetes cluster.

Pre-requisites
--------------
Ansible 2.8 and greater. This playbook was tested with Ansible 2.9.1 and Podman 1.4.4 on RHEL 7.5

```
[root@webserver roles]# ansible --version
ansible 2.9.1

[root@webserver roles]# podman --version
podman version 1.4.4
```

Clone the repo and run `ansible-playbook webmail-setup.yml`

The playbook consists of three roles:
  setup-local-registry
    Sets up a local Docker registry using the docker-distribution package

  setup-rainloop
    Installs Podman, pulls a Ubuntu 19.10 image and installs Python3 in it. The container is named rainloop

  build-rainloop
    Configures the `rainloop` container with Rainloop and Nginx. 

