pipeline {
    agent any

    stages {
        stage('scm') {
            steps {
                https://github.com/satankumar/jenkins.git
            }
       }
        stage('docker build') {
            steps {
                sh 'sudo docker build  -t  satan12345/pipeline:v1'
            }
        }
        stage('docker images') {
            steps {
                sh 'sudo docker images'
            }
        }
        stage('docker rm') {
            steps {
                sh 'sudo docker rm -f pipe2'
            }
        }
        stage('docker run') {
            steps {
                sh 'sudo docker run -d --name pipe2  -p 8089:80 satan12345/pipeline:v1'
            }
        }
        stage('docker login') {
            steps {
                sh 'sudo docker login -u ${dockerhub_username} -p ${dockerhub_password}'
            }
        }
        stage('docker push') {
            steps {
                sh 'sudo docker push satan12345/pipeline:v1'
            }
        }
        stage('print success') {
            steps {
                sh 'echo success'
            }
        }
    }
}

