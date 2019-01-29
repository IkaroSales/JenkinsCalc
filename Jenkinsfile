pipeline {
    agent any
    stages {
        stage('Build (Compiling)') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('Unit Test (JUnit)'){
        	steps{
        		sh 'mvn install test'
        	}
        }
    }
}
