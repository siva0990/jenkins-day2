
pipeline {
    agent any

    stages {
        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }

        stage('Terraform Apply') {
            when {
                branch 'master'
            }
            steps {
                input message: 'Do you approve Terraform Apply?'
                sh 'terraform apply -auto-approve'
            }
        }
    }
}

