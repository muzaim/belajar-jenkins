pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the repository...'
                checkout scm
            }
        }

        stage('Deploy HTML') {
            steps {
                echo 'Copying HTML files to /var/jenkins_home/html-deploy'
                sh '''
                    mkdir -p /var/jenkins_home/html-deploy
                    cp *.html /var/jenkins_home/html-deploy/
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment successful.'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
