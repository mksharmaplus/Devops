pipeline {
    agent any

    stages {
        stage('checkout code') {
            steps {
              checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Rahul-training/Devops.git']])
       
            }
        }
        stage('Install Maven Build Tool') {
            steps {
              sh 'wget https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.tar.gz'
              sh 'tar -xzvf /var/lib/jenkins/workspace/myproject/apache-maven-3.9.4-bin.tar.gz'
       
            }
        }
        stage('Compile Sample Application') {
            steps {
              sh dir('/var/lib/jenkins/workspace/myproject/addressbook/addressbook_main'){
                sh '/var/lib/jenkins/workspace/myproject/apache-maven-3.9.4/bin/mvn compile'
       
            }
        }
        
     }
    }
}
