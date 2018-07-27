pipeline {
    agent any

    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage('Build'){
            steps {
                build job: 'deploy-to-staging'
            }
        }
    }
}
