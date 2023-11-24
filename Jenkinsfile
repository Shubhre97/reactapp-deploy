pipeline {
    agent any

    stages {
        stage('Code Checkout'){
            git branch: 'main', url: 'https://github.com/Shubhre97/reactapp-deploy'
        }

        stage('Code Scanning') {
        
        steps { echo 'sonar-scanner' }

        }

        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm install'
                sh 'npm run build'
                 } // steps install-dependencies closed
        } // stage install-dependencies closed
        
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}