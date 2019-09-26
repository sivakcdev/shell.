pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Docker') {
            steps {
                sh 'docker build -t ubuntu:v1.0.0 .'
            }
        }
		stage('Creating Container') {
            steps {
                sh 'docker run -dt --name shivakc ubuntu:v1.0.0 /bin/bash '
            }
        }
		stage('creating custom images') {
            steps {
                sh 'docker commit shivakc  ubuntu:v1.0.0'
            }
        }
	

	
    }
	
}
