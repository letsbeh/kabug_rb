pipeline {
    agent {
        docker {
            image 'qaninja/rubywd'
        }
    }
    
    stages {
        stage('Build') {
            steps {
                echo'Building or Resolve Dependencies!'
                sh 'rm -f Gemfile.lock'
                sh 'bundler install'
            }
        }
        stage('Teste') {
            steps {
                echo 'Running regression Test'
                sh 'bundle exec cucumber -p ci'
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
