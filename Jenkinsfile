pipeline {
    agent any

    stages {
        stage('Build'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps
            {
                sh '''
                    ls -la
                    npm --version
                    node --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
        stage('test'){
            echo 'test stage'
            sh '''
                test -f build/index.html
                npm test
           '''
        }
    }
}
