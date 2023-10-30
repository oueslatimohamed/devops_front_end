pipeline {
    agent any

    stages {
       
        stage('Checkout Frontend') {
            steps {
                script {
                    checkout([$class: 'GitSCM', branches: [[name: 'master']], userRemoteConfigs: [[url: 'https://github.com/oueslatimohamed/devops_front_end.git']]])
                }
            }
        }

        stage('Build Frontend') {
            steps {
                sh 'npm install && ng build'
            }
        }
       stage('Checkout Backend') {
            steps {
                script {
                    checkout([$class: 'GitSCM', branches: [[name: 'master']], userRemoteConfigs: [[url: 'https://github.com/oueslatimohamed/devops_back_end.git']]])
                }
            }
        }

        stage('Build Backend') {
            steps {
                sh 'mvn clean install'
            }
        }

    }
}
