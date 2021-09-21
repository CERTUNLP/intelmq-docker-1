# intelmq-docker

## THIS STEP

## Run & deploy containers in dev mode:

## Fastest way to run & deploy

## For developers

1. `cd ~`
0. `sudo apt update && sudo apt upgrade -y && sudo apt install docker.io git docker-compose`
0. `git clone https://github.com/certat/intelmq-docker.git --recursive`
0. `cd intelmq-docker`
0. `docker-compose pull`
0. In next step replace git@github.com:certtools/intelmq.git by your fork of intelmq
0. `git clone git@github.com:certtools/intelmq.git my_fork_of_intelmq/`
2. `docker-compose -f docker-compose-dev.yml up`
3. Open your favourite browser -> Go to `http://127.0.0.1:1337/`


## Docker-compose-dev.yml file

### Volume:

**./my_fork_of_intelmq/:/etc/intelmq** -> this is the folder where your source code need to be, we decide to use fork from intelmq so you could inherit intelmq changes and upgrades to your bots code directly.

**./dev_tools/:/opt/dev_tools** -> folder for special commands required to apply your changes in runtime

### Add your own bots

Just start coding or pull your bots repository in ./my_fork_of_intelmq folder

### How to install and look yours bots runnig


Just run /opt/dev/update.sh in the container:

1. `docker-compose exec -f docker-compose-dev.yml  intelmq sudo bash /opt/dev_tools/install_reqs_and_deploy_bots`

When you do this:

* Yours bots and REQUERIMENTS will be installed
