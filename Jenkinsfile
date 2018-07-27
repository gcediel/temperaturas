pipeline {
    agent any
    stages {
        stage("Docker build") {
            steps {
                sh "docker -H 192.168.0.11:2375 build -t quercus.elbor.org:5000/temperaturas:${BUILD_TIMESTAMP} ."
            }
        }
        stage("Docker push") {
            steps {
                sh "docker -H 192.168.0.11:2375 push quercus.elbor.org:5000/temperaturas:${BUILD_TIMESTAMP}"
            }
        }
        stage("Docker run") {
            steps {
                sh "docker -H 192.168.0.11:2375 run -d -p 9080:5000 temperaturas:${BUILD_TIMESTAMP}"
            }
        }
    }
}
