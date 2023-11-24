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
        
        stage('Pushing to S3 & CloudFront Distribution') {
            steps {
              sh "aws configure set region $AWS_DEFAULT_REGION" 
              sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID"  
              sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
              sh "aws s3 sync build/  s3://reactapp-deploy-24"
              sh "aws cloudfront create-invalidation \
                 --distribution-id EIYKMF8QKCBXH \
                 --paths '/*' "
                
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}