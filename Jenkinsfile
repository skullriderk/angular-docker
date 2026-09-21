pipeline {
    agent any

    stages {
        stage('Code Checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/skullriderk/angular-docker.git'
            }

      
        }
        stage('Docker image'){
              steps {
            sh 'docker build -t angular:v${BUILD_NUMBER} .'
              }
        }
           stage('Docker Container'){
                 steps {
                 sh 'docker stop angular || true'
                sh 'docker rm angular || true'
            sh 'docker run -itd --name angular -p 8082:4200 angular:v${BUILD_NUMBER}'
                 }
        }
    }

}
