# Jenkins-demo2

https://www.jenkins.io/doc/book/pipeline/docker/

multi-conatiner:
```
pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker { image 'maven:3.9.9-eclipse-temurin-21-alpine' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:20.18.0-alpine3.20' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
```
