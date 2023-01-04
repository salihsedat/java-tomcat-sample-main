pipeline {
    agent any
    stages {
        stage('Build Application') {
             steps{
                build job: 'build-web-application2'
            }
        }
        stage('Deploy to Staging Environment'){
            steps{
                build job: 'Deploy-Application-Staging-Environment2'
            }            
        }
        stage('Deploy to Production Environment'){
            steps{
                timeout(time:5, unit:'DAYS'){
                    input message:'Approve PRODUCTION Deployment?'
                }
                build job: 'Deploy-Application-Production-Environment2'
            }
        }
    }
}
