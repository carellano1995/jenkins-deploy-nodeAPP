pipeline {
    agent any
    tools {nodejs "NODE 16.7.0"}

    stages {
        stage('Build') { 
            steps { 
                sh 'npm install' 
            }
        }
        stage('Test'){
            steps {
                sh 'make check'
                junit 'reports/**/*.xml' 
            }
        }
        stage('Deploy') {
            steps {
                sh 'make publish'
            }
        }
    }
}
// Script //
node {
    stage('Build') {
        sh 'make'
    }

    stage('Test') {
        sh 'make check'
        junit 'reports/**/*.xml'
    }

    stage('Deploy') {
        sh 'make publish'
    }
}