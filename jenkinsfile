pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/devopsbeginner/maven_project.git'
            }
        }

        stage('Build with Maven') {
            steps {
                dir('hello-maven') {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Deploy using Ansible') {
            steps {
                sh 'ansible-playbook -i hosts deploy-local-jar.yml'
            }
        }
    }
}

