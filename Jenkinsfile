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
            
		post{
			always{
					junit '**/surefire-reports/*.xml'
        			cucumber buildStatus: 'UNCHANGED', customCssFiles: '', customJsFiles: '', failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: 'target/cucumber.json', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1    
     			   }
     	}

      }
    }

  

