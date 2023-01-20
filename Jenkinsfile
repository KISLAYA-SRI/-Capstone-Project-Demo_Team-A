pipeline {
    agent any
    tools {
        terraform 'terraform'
    }
    stages {
        stage('terraform format') {
            when {
                expression {action == 'apply'}
            }
            steps {
                sh 'terraform fmt'
            }
        }
        stage('terraform initialize') {
            when {
                expression {action == 'apply'}
            }
            steps{
                sh 'terraform init'
            }
        }
        stage('terraform validate') {
            when {
                expression {action == 'apply'}
            }
            steps{
                sh 'terraform validate'
            }
        }
        stage('terraform plan') {
            when {
                expression {action == 'apply'}
            }
            steps{
                sh 'terraform plan'
            }
        }
        stage('terraform apply') {
            when {
                expression {action == 'apply'}
            }
            steps{
                sh 'terraform apply --auto-approve'
            }
        }
        stage('terraform destroy') {
            when {
                expression {action == 'destroy'}
            }
            steps{
                script {
                    sh 'terraform destroy --auto-approve'
                }
            }
        }
    }
}
