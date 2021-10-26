pipeline {
    agent any

    stages {
        stage('SCM') {
          steps {
//                 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ewansheldon', url: 'git@github.com:ewansheldon/jenkins-test.git']]])
                sh "git clone git@github.com:ewansheldon/spring-project.git"
          }
        }
        stage('Test') {
            steps {
                sh "./gradlew test"
            }
        }
    }
}