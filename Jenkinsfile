pipeline {
    agent any
    stages {
        stage('Build (Compiling)') {
            steps {
                sh 'mvn clean install package'
            }
        }
        stage('Unit Test (JUnit)') {
        	steps {
        		sh 'mvn test'
        	}
        }
        stage('Deploy Artifact (Nexus)') {
            steps {
                sh 'mvn deploy:deploy-file -DgroupId=my.group.id \
                    -Dversion=1.0.0.1 \
                    -Dpackaging=jar \
                    -Dfile=target/CalcDemoJenkins-0.0.1-SNAPSHOT.jar \
                    -DgeneratePom=true \
                    -Durl=http://localhost:8081/repository/maven-releases/'
            }
        }
    }
}
