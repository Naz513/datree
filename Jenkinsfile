pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Naz513/datree.git', branch: 'master'
            }
        }
        stage('Install Datree') {
            steps {
                sh 'ls'
            }
        }
        stage('Testing for Misconfigs') {
            steps {
                script{
                    withEnv(['DATREE_TOKEN=$DATREE_TOKEN']) {
                        sh 'datree test main.yaml'
                    }
                }
            }
        }
    }
}