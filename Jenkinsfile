pipeline {
    agent any

    stages {

        stage('Build') {
            agents{
                docker{
                    image 'node 18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls-la
                    npm --version
                    node --version
                    npm ci
                    npm build
                    ls-la
                '''
            }
        }
    }
}