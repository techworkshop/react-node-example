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
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}