pipeline {
    agent any

    stages {
        stage('clean workspace') {
          steps {
                cleanWs()
          }
        }
        stage('SCM') {
          steps {
//                 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ewansheldon', url: 'git@github.com:ewansheldon/jenkins-test.git']]])
                sh "git clone https://github.com/ewansheldon/spring-project.git"
                sh "cd spring-project"
          }
        }
        stage('Test') {
            steps {
                sh "./gradlew test"
            }
        }
    }
}