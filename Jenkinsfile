pipeline {
    agent {
        docker {
            image 'registry.nicolo.info/myjenkins-agent:latest'
            label 'maven-agent'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                // This step checks out the SCM content into the workspace.
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // This step runs the Maven build.
                sh 'mvn -B clean package'
            }
        }
        stage('Test') {
            steps {
                // This step runs the Maven test.
                sh 'mvn test'
            }
        }
        // Further stages like 'Deploy' can be added here.
    }
}
