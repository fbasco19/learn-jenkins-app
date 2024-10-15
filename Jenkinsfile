pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            } 
        }
        stage('Test') {
            steps {
                sh '''
                    echo "Test stage"
                    ls -l "build/index.html"
                    find build/index.html -name "index.html"
                    npm test a
                '''
                 }  
                     }
            }
    }
