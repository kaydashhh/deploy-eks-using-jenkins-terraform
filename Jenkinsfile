pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="859888346862"
        AWS_DEFAULT_REGION="us-east-2"     
    }
    stages {
        
        stage('Deploy EKS cluster') {
            environment {
                AWS_ACCESS_KEY_ID = credentials('aws-access-key-id')
                AWS_SECRET_ACCESS_KEY = credentials('aws-secret-access-key')
            }
            
            steps {
                sh 'terraform init'
                sh 'terraform plan -out=eks.tfplan'
                sh 'terraform apply -auto-approve eks.tfplan'
            }
        }
        
    }
}
