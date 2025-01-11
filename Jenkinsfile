pipeline {
    agent any  // Run on any available agent (machine)

		tools {
				maven 'Maven 3.x'
				
			}
					
        stages {
        
               stage('Build')
               {
               steps
               {
               bat 'mvn clean install'
               }
               
               }
        stage('Run Test') {
            steps {
                // Run tests (e.g., using Maven)
                bat 'mvn clean test'
            }
            stage('Archive Results')
            steps
            {
            
            }
            
        }

      }
    }

  

