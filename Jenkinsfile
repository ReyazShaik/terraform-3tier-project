pipeline {
    agent any 

    parameters {
        choice(name: 'ACTION', choices: ['apply', 'destroy'], description: 'Terraform action')
    }

    environment {
        AWS_ACCESS_KEY_ID     = credentials('ur access key')
        AWS_SECRET_ACCESS_KEY = credentials('ur secret key1')
    }

    stages {

        stage('checkout') {
            steps {
                git 'https://github.com/NareshKeerapatla/terraform-3tier-project.git'
            }
        }

        stage('init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('validate') {
            steps {
                sh 'terraform validate'
            }
        }

        stage('plan') {
            steps {
                sh 'terraform plan'
            }
        }

        stage('apply/destroy') {
            steps {
                sh "terraform ${ACTION} --auto-approve"
            }
        }
    }
}
