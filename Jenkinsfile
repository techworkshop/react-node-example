pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                echo 'Checkout..'
                sh 'git fetch'
                sh 'git checkout master'
                sh 'git reset --hard origin/master'
            }
        }
        stage('install'){
            steps {
                echo 'installing node dependencies..'
                sh 'whoami'
                sh 'sudo npm install'
                echo 'node dependencies are installed'
            }
        }
        stage('pre-build unit test'){
            steps {
                echo 'executing unit test before building docker image..'
                sh 'npm run test'
                echo 'unit test completed'
            }
        }
        stage('Build') {
            steps {
                echo 'Building Docker Image..'
                sh 'docker build --rm -f Dockerfile -t react-node-example:latest .'
                echo 'docker image building is done'
            }
        }
        stage('Test') {
            steps {
                echo 'Running Docker Container from the image created...'
                sh 'docker run -d -p 3000:8080 --name react-node-example react-node-example'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}