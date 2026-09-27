# gitlab-onprem
Setup GitLab as a self-hosted server
## Setup
Spin up infra (EC2, DigitalOcean Droplet, etc) minimum specs 8GB RAM
Ensure Docker & Docker Compose plugin installed
mkdir /srv/gitlab
export GITLAB_HOME=/srv/gitlab
setup DNS entry for your new gitlab server (CloudFlare easy for this, raw DNS not proxy if so)
`docker compose up -d`
wait about 10 min for things to initialize

## Teardown
`docker compose down`
rm -rf $GITLAB_HOME
