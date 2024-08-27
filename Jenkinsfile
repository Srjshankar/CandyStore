pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Srjshankar/CandyStore.git']]) 
            }
        }
        stage('docker') {
            steps {
                script {
                 withDockerRegistry(credentialsId: 'hello') {
                         sh 'docker build -t shankar9/candystore .'
                         sh 'docker push shankar9/candystore:latest'
                   }
               }
            }
        }
    }
}
