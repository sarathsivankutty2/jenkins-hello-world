pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven M3"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
               git branch: 'main', credentialsId: 'ab4c8315-af2a-4044-8db4-e8970837ac37', url: 'https://github.com/sarathsivankutty2/jenkins-hello-world.git'

                // Run Maven on a Unix agent.
                sh "mvn clean package -DskipTests=true"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('Unit Test') {
            steps {
                // Run unit tests
                sh "mvn test"
            }
        }
    }
}
