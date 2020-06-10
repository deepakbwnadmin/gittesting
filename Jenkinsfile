pipeline {
    
    // Variables:
    environment {
        project = "repco"
        region = "ap-southeast-2"

        gitCredentialsId = '02b20525-172e-41a1-9367-a5ab361aac5d'
        gitRepo = 'https://github.com/deepakbwnadmin/gittesting.git'

        build_name = "Deploy_${env.ENV}_${env.COMMIT_ID}_${env.BUILD_NUMBER}"
 }


    // Build stages:
    stages {

        stage('Fetch code') {
            steps {
                // Normal git does not work with commitIDs, so use the script syntax
                script {
                    // Set build name
                    currentBuild.displayName = "${env.build_name}"

                    }
    
                    // Fetch code:
                    checkout([
                        $class: 'GitSCM', branches: [[name: params.COMMIT_ID ]],
                        userRemoteConfigs: [[
                            url: "${env.gitRepo}",
                            credentialsId: "${env.gitCredentialsId}"
                        ]],
                    ])

                }
            }
        }

        stage('Copy repo to /data') {
            steps {
                sh "cp -r /root/pipelinetest /data/"
            }
        }        
    }
