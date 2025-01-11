pipeline {
    agent any  // Run on any available agent (machine)

    tools {
        maven 'Maven 3.x'  // Ensure Maven is configured in Global Tool Configuration
    }

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean install'  // Use 'sh' for Linux/Mac systems
            }
        }
        
        stage('Run Test') {
            steps {
                bat 'mvn clean test'
            }
            post {
                always {
                    junit '**/surefire-reports/*.xml'  // Collect test results
                    cucumber(
                        buildStatus: 'UNCHANGED', 
                        fileIncludePattern: 'target/cucumber.json',
                        sortingMethod: 'ALPHABETICAL'
                    )
                }
            }
        }
    }
}