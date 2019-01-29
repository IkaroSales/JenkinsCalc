pipeline {
    agent any
    stages {
        stage('Build (Compiling)') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('Unit Test (JUnit)') {
        	steps {
        		sh 'mvn install test'
        	}
        }
        stage('Deploy Artifact (Nexus)') {
            steps {
                sh 'mvn deploy:deploy-file -DgroupId=my.group.id \
                    -DartifactId=my-artifact-id \
                    -Dversion=1.0.0.1 \
                    -Dpackaging=jar \
                    -Dfile=target//*.jar \
                    -DgeneratePom=true \
                    -DrepositoryId=my-repo \
                    -Durl=http://localhost:8081/repository/maven-releases/'
            }
        }
    }
}
