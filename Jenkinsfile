pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Image') {
            steps {
                bat 'docker build -t myapp .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker rm -f myapp 2>NUL || ver >NUL'
                bat 'docker run -d --name myapp -p 8081:80 myapp'
            }
        }
    }
}