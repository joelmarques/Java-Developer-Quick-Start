# Java-Developer-Quick-Start

*Esse guia foi baseado no Linux/Ubuntu 20.04 LTS

## Objetivo
Disponibilizar um guia rápido de todas as configurações/instalações necessárias para os desenvolvedores começarem a desenvolver suas atividades diárias.

## Git
```
$ sudo apt update
$ sudo apt install git-all
$ git --version
$ git config --global user.name "SEU_NOME"
$ git config --global user.email "SEU_EMAIL"
```
## Java 11
Baixe: jdk-11.0.9_linux-x64_bin.tar.gz

Link: https://www.oracle.com/java/technologies/javase-jdk11-downloads.html
```
$ cd Downloads
$ sudo tar zxvf jdk-11.0.9_linux-x64_bin.tar.gz
$ sudo mv jdk-11.0.9 /opt/
$ sudo chmod 777 -R /opt/jdk-11.0.9/
$ sudo gedit /etc/profile
```
```
export JAVA_HOME="/opt/jdk-11.0.9"
export CLASSPATH="$JAVA_HOME/lib":$CLASSPATH
export PATH="$JAVA_HOME/bin":$PATH
```
```
$ source /etc/profile
$ java --version
$ echo $JAVA_HOME
```
## Maven
```
$ cd Downloads
$ wget https://downloads.apache.org/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
$ sudo tar zxvf apache-maven-3.6.3-bin.tar.gz
$ sudo mv apache-maven-3.6.3 /opt/
$ sudo chmod 777 -R /opt/apache-maven-3.6.3
$ sudo gedit /etc/profile
```
```
Adicionar o comando a baixo na linha final da página que se abriu, salvar e sair. 

export M2_HOME="/opt/apache-maven-3.6.3"
export PATH=$M2_HOME/bin:$PATH
```
```
$ source /etc/profile
$ mvn -v
```

## Docker
```
$ sudo apt install docker
$ sudo apt install docker.io
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

## Mongo
```
$ sudo apt install mongodb
$ mongo -version
```

## Mongo Compass (Mongo Client)

```
$ cd Downloads
$ wget https://downloads.mongodb.com/compass/mongodb-compass_1.23.0_amd64.deb

$ sudo dpkg -i mongodb-compass_1.23.0_amd64.deb
```

## Insomnia (API Client)
```
$ sudo snap install insomnia
```

## Intellij
```
$ sudo apt update
$ sudo snap install intellij-idea-community --classic
```
