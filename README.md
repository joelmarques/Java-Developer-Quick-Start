# Work Environment Setup (ubuntu) 🔨⚡

*This guide was based on Linux/Ubuntu 22.04 LTS

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
$ git config --global user.email "YOUR-EMAIL"
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
$ sdk install java 17.0.7-oracle
$ sdk default java 17.0.7-oracle
```

## Maven with sdkman
```
$ sdk list maven
$ sdk install maven 3.9.2
$ mvn -version
```

## Gradle with sdkman
```
$ sdk list gradle
$ sdk install gradle 8.1.1
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

## DBeaver
```
$ sudo snap install dbeaver-ce
```

## Google Chrome
```
$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
$ sudo dpkg -i google-chrome-stable_current_amd64.deb
```

## Slack
```
$ sudo snap install slack
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
$ ssh-keygen
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

## Mongo

*Para instalar direto na máquina:
```
$ sudo apt install mongodb
$ mongo -version
```

*Para instalar com docker:
```
$ sudo docker pull mongo

$ sudo docker run --name container_mongo -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=mongo_user -e MONGO_INITDB_ROOT_PASSWORD=mongo_pass -e MONGO_INITDB_ROOT_DATABASE=mongo_db mongo

*Use in application.properties
spring.data.mongodb.uri=mongodb://mongo_user:mongo_pass@localhost:27017/mongo_db?authSource=admin
```

## Mongo Compass (Mongo Client)

```
$ cd Downloads
$ wget https://downloads.mongodb.com/compass/mongodb-compass_1.23.0_amd64.deb

$ sudo dpkg -i mongodb-compass_1.23.0_amd64.deb
```

## References 👨‍🏫
[Configure AWS Cli] https://docs.aws.amazon.com/pt_br/cli/latest/userguide/cli-configure-quickstart.html

## That's all
Hope you enjoy it.
