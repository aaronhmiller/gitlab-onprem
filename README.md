# gitlab-onprem
Setup GitLab as a self-hosted server

## Setup
* Spin up infra (EC2, DigitalOcean Droplet, etc) minimum specs 8GB RAM
* Ensure Docker & Docker Compose plugin installed
* mkdir /srv/gitlab
* export GITLAB_HOME=/srv/gitlab
* edit the docker-compose.yml file to match your gitlab server's hostname (i.e. gitlab<n>.example.com)
* setup DNS entry for your new gitlab server (CloudFlare easy for this, raw DNS not proxy if so)
* `docker compose up -d`
* wait about 10 min for things to initialize

## Connecting to CodeRabbit
* app.coderabbit.ai choose "GitLab Self-hosted"
* Generate a Personal Access Token (PAT) within GitLab
* Onboard using the automated method

## Teardown
* `docker compose down`
* rm -rf $GITLAB_HOME
* make a mental note to increment the value of your hostname

## Miscellaneous
* if you forget to incremement the host in your DNS, you can do that and then run `docker exec -it gitlab gitlab-ctl reconfigure`
