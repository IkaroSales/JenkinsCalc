pipeline {
    agent any {
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('test'){
        	steps{
        		sh 'mvn install test'
        	}
        }
    }
}
