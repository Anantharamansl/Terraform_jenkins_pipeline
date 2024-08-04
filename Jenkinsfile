pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID     = credentials('accesskey')
        AWS_SECRET_ACCESS_KEY = credentials('secretkey')
        AWS_DEFAULT_REGION    = 'ap-south-1'
    }


    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Anantharamansl/Terraform_jenkins_pipeline.git'
            }
        }
           stage('Terraform init') {
            steps {
                sh 'terraform init'
            }
        }
           stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }           
           stage('terraform apply') {
           steps {
               sh 'terraform apply --auto-approve'
            }
        }
    }
}
