pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Naz513/datree.git', branch: 'master'
            }
        }
        stage('Integration Test') {
            steps {
                sh 'echo $DATREE_TOKEN'
            }
        }
        stage('Testing for Misconfigs') {
            steps {
                script{
                    withEnv(['DATREE_TOKEN=$DATREE_TOKEN']) {
                        sh 'datree test *.yaml --only-k8s-files'
                    }
                }
            }
        }
    }
}