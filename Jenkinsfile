pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'ewan and maciej are building..'
            }
        }
        stage('SCM') {
          steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ewansheldon', url: 'git@github.com:ewansheldon/jenkins-test.git']]])
                sh "ls -lart ./*"
          }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}