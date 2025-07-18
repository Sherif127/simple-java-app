pipeline{
    agent any

    stages{
        stage('build'){
            steps{
                script{
                    echo "build in progress"
                }
            }
        }
        stage('test'){
            steps{
                script{
                    echo "test in progress"
                }
            }
        }
    }
    post {
        success {
            slackSend channel: '#jenkins-ci', color: '#439FE0', message: ' "Build Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}"', teamDomain: 'mycompany-npv1033', tokenCredentialId: 'jenkins-slack'  }
        failure {
            slackSend channel: '#jenkins-ci', color: '#439FE0', message: ' "Build Failed: ${env.JOB_NAME} ${env.BUILD_NUMBER}"', teamDomain: 'mycompany-npv1033', tokenCredentialId: 'jenkins-slack'  }
        }
    }

}