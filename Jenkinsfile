pipeline {
    agent {
  label 'java'
}
tools {
  maven 'maven3'
}
 stages{
        stage ('Checkout') {
            steps{
                checkout poll: false, scm: scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/its-varthini/SpringbootMaven-Jenkins-Demo-varthini.git']])
            }
            
        }
        stage ('Build') {
            steps {
                echo "Build Stage is in progress"
                sh 'mvn compile'
            }
            
        }
        stage ('Test'){
            steps {
                echo "Test Stage is in progress"
                sh 'mvn test'
                junit '**/target/surefire-reports/*.xml'
            }
            
       }
    }
}

