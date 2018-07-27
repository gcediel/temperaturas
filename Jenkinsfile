pipeline {
    agent any
    stages {
        stage("Compile") {
            steps {
            }
        }
        stage("Unit test") {
            steps {
            }
        }
        stage("Code coverage") {
            steps {
            }
        }
        stage("Static code analysis") {
            steps {
        }
        stage("Package") {
            steps {
            }
        }
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
            step= {
                sh "docker -H 192.168.0.11:2375 run -d -p 9080:5000 quercus.elbor.org:5000/temperaturas:${BUILD_TIMESTAMP}"
            }
        }
        stage("Acceptance test") {
            steps {
            }
        }
	}
}
