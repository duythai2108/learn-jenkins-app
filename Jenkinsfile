pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "Without docker"
                    ls -la
                    touch container-no.txt
                '''
            }
        }
        stage('w/ docker') {
            agent {
                docker {
                    image 'node:24-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "With docker"
                    ls -la
                    touch container-yes.txt
                '''
            }
        }
    }
}
