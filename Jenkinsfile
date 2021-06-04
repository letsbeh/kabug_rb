pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo'Building or Resolve Dependencies!'
                sh 'bundler install'
            }
        }
        stage('Teste') {
            steps {
                echo 'Running regression Test'
            }
        }
        stage('UAT') {
            steps {
                echo 'Wait for user acceptance'
                input(message: 'Go to production?', ok: 'Yes')
            }
        }
        stage('Prod'){
            steps{
                echo 'Webapp is ready'
            }
        }
    }
}

