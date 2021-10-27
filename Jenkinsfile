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
//                 sh "git clone https://github.com/ewansheldon/spring-project.git"

//                checkout BbS(branches: [
//                        [name: 'emr/bugfix/11.52/PE-140379-view-meds-trunk']
//                ],
//                        credentialsId: 'builduser99',
//                        extensions: [
//                                [$class : 'CheckoutOption',
//                                 timeout: 120
//                                ],
//                                [$class      : 'CloneOption',
//                                 honorRefspec: true,
//                                 noTags      : true,
//                                 timeout     : 120
//                                ],
//                                [$class: 'PruneStaleBranch'],
//                                [$class: 'DisableRemotePoll'],
////                                [$class: 'LocalBranch', localBranch: 'emr/bugfix/11.52/PE-140379-view-meds-trunk']
//                        ],
//                        id: '51b38292-79e6-46ad-ba39-7c8642238e41',
//                        mirrorName: '',
//                        projectName: 'EMR',
//                        repositoryName: 'emr',
//                        serverId: 'a2a6eba9-482f-4319-9806-fd50d236fa0d')

                withCredentials([usernamePassword(credentialsId: 'builduser99', passwordVariable: 'builduserpass', usernameVariable: 'builduser')]) {
                    sh 'git clone --depth 1 https://${builduser}:${builduserpass}@bitbucket.eclinicalworks.com/scm/emr/emr.git --branch "bugfix/11.52/PE-140379-view-meds-trunk" '
                }
            }
        }
        stage('Test') {
            steps {
                sh 'echo skip'
                sh '''
                    cd emr/server
                    ./gradlew cpoe:test
                   '''
            }
        }
    }
}