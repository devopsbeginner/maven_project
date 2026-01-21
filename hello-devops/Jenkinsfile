pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build with Maven') {
            steps {
                dir('app') {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Deploy using Ansible') {
            steps {
                dir('ansible') {
                    sh 'ansible-playbook -i inventory deploy.yml'
                }
            }
        }
    }
}
