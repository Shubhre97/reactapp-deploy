pipeline {
    agent any

    stages {
        stage('Code Checkout'){
            steps{
            git branch: 'main', url: 'https://github.com/Shubhre97/reactapp-deploy'}
        }

        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm install'
                sh 'npm run build'
                 } // steps install-dependencies closed
        } // stage install-dependencies closed
        
        stage('Pushing to S3') {
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