pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Naz513/datree.git', branch: 'master'
            }
        }
        stage('Testing for Misconfigs') {
            steps {
                sh 'curl https://get.datree.io | /bin/bash'
                script{
                    withEnv(['DATREE_TOKEN=$DATREE_TOKEN']) {
                        sh 'datree test *.yaml --only-k8s-files'
                    }
                }
            }
        }
    }
}