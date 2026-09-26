pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Verify WAR') {
            steps {
                sh 'ls -lh target/'
            }
        }
    }

    post {

        success {
            echo 'Maven WAR build successful!'
        }

        failure {
            echo 'Maven WAR build failed!'
        }
    }
}
