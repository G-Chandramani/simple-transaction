pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {   
		 git branch : 'main',
			url: 'https://github.com/G-Chandramani/simple-transaction.git'
		}
	}

        stage('Build Docker Images') {
            steps {
                sh 'docker-compose build'
            }
        }

	stage('Stop Old Containers') {
	   steps {
		sh 'docker-compose down'
		}
	}

        stage('Deploy Containers') {
            steps {
                sh 'docker-compose up -d'
            }
        }

    }
}
 
