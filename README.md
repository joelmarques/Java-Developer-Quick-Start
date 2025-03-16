# Work Environment Setup (ubuntu) 🔨⚡

*This guide was based on Linux/Ubuntu 24.04 LTS

## Goal
Provide a quick guide of all necessary configurations/installations for developers to start developing their daily tasks.

## Update the system repository
```
$ sudo apt update
```

## Git
```
$ sudo apt install git-all
$ git --version
$ git config --global user.name "YOUR_NAME"
$ git config --global user.email "YOUR_EMAIL"
$ git config --list
```

## Curl, zip and unzip
```
$ sudo apt install curl zip unzip
```

## Sdkman
```
$ curl -s "https://get.sdkman.io" | bash
$ source "$HOME/.sdkman/bin/sdkman-init.sh"
$ sdk version
```

## Java with sdkman
```
$ sdk list java
$ sdk install java 21.0.6-oracle
$ sdk default java 21.0.6-oracle
```

## Maven with sdkman
```
$ sdk list maven
$ sdk install maven 3.9.9
$ mvn -version
```

## Gradle with sdkman
```
$ sdk list gradle
$ sdk install gradle 8.12.1
$ gradle -v
```

## Intellij
```
$ sudo snap install intellij-idea-community --classic
```

## Insomnia (API Client)
```
$ sudo snap install insomnia
```

## Postman (API Client)
```
$ sudo snap install postman
```

## Python
```
$ sudo add-apt-repository ppa:deadsnakes/ppa
$ sudo apt update
$ sudo apt install python3
$ python3 --version
$ sudo apt install -y python3-pip
$ pip3 --version
```

## Docker
```
$ sudo snap install docker
$ sudo apt install docker.io
$ sudo usermod -aG docker ${USER}
$ su - ${USER}
$ docker -v
```

## Docker Compose
```
$ sudo apt install docker-compose
$ docker-compose -v
```

## Kubectl
```
$ cd Downloads
$ curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
$ ls
$ sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
$ kubectl version
```

## Node
```
$ sudo apt install nodejs
$ node -v
```

## NPM
```
$ sudo apt install npm
$ npm -v
```

## Postgres
```
$ docker pull postgres
$ docker run --name postgres -e POSTGRES_PASSWORD=postgres -d postgres
$ docker ps -a
```

## DBeaver (SQL Client)
```
$ sudo snap install dbeaver-ce
```

## Mongo
```
$ docker pull mongo
$ docker run --name mongo -d mongo:latest
$ docker ps -a
```

## Mongo Compass (Mongo Client)
```
$ cd Downloads
$ wget https://downloads.mongodb.com/compass/mongodb-compass_1.45.3_amd64.deb
$ sudo dpkg -i mongodb-compass_1.45.3_amd64.deb
```

## Google Chrome
```
$ cd Downloads
$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
$ sudo dpkg -i google-chrome-stable_current_amd64.deb
```

## Slack
```
$ sudo snap install slack
```

## FortiClient VPN

```
# Download libappindicator1
$ wget http://mirrors.kernel.org/ubuntu/pool/universe/liba/libappindicator/libappindicator1_12.10.1+20.10.20200706.1-0ubuntu1_amd64.deb 

# Download dependency required by libappindicator1
$ wget http://mirrors.kernel.org/ubuntu/pool/universe/libd/libdbusmenu/libdbusmenu-gtk4_16.04.1+18.10.20180917-0ubuntu8_amd64.deb

# Install both packages
$ sudo apt install  ./libappindicator1_12.10.1+20.10.20200706.1-0ubuntu1_amd64.deb ./libdbusmenu-gtk4_16.04.1+18.10.20180917-0ubuntu8_amd64.deb 

# Install forticlient downloaded from https://www.fortinet.com/support/product-downloads
$ sudo apt install ./forticlient_vpn_7.4.0.1636_amd64.deb
```


## AWS VPN Client
```
$ curl https://d20adtppz83p9s.cloudfront.net/GTK/latest/awsvpnclient_amd64.deb -o awsvpnclient_amd64.deb
$ sudo dpkg -i awsvpnclient_amd64.deb
$ wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.0g-2ubuntu4_amd64.deb
$ sudo dpkg -i libssl1.1_1.1.0g-2ubuntu4_amd64.deb
```

## AWS Cli
```
$ sudo snap install aws-cli --classic
```

## Configure VPN
```
Open the AWS VPN Client app > File > Manage Profiles > Add Profile
Display Name: name
VPN Configuration File: browse to the configuration file that you received from your Client VPN  administrator
Add Profile > Done > Connect
```

## Configure AWS Keys
```
$ aws configure
```
```
AWS Access Key ID [None]: your_aws_access_key_id
AWS Secret Access Key [None]: your_aws_secret_access_key
Default region name [None]: us-west-1
Default output format [None]: json
```
```
$ aws s3 ls
```

## Configure SSH Key on Github
Generate key
```
$ ssh-keygen -t rsa -b 4096
```
Open the file and change your email at the end of the file
```
$ gedit .ssh/id_rsa.pub
```
Example: “...j4O0ECgAbJRFSgCnes= user_name@computer_name” change by “...j4O0ECgAbJRFSgCnes= your_professional_email”
```
Copy and Paste on the Github > Settings > SSH and GPG keys > New SSH key
Title: my_sshkey
Key type: Authentication Key
Key: your_sshkey_content
```

## References 👨‍🏫
- [Configure AWS Cli] https://docs.aws.amazon.com/pt_br/cli/latest/userguide/cli-configure-quickstart.html
- [Configure Kubectl] https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

## That's all
Hope you enjoy it.
