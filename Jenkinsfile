currentBuild.displayName = "Final_Demo # "+currentBuild.number


        

pipeline{
        agent any  
        
        
        stages{


              stage('Quality Gate Statuc Check'){

              
                  steps{
                      script{
                      withSonarQubeEnv('sonar') { 
                      sh "mvn sonar:sonar -Dsonar.projectKey=sample-java-web -Dsonar.host.url=http://34.75.25.98 -Dsonar.login=8a677eec1eebd72822b74d567f37ddcc0e981997"
                       }
                      timeout(time: 2, unit: ‘MINUTES’) {
                        waitForQualityGate abortPipeline: true
                      }
                    }
		    sh "mvn clean install"
                  }
                }  
              }



              
		 
			
		
               }
	      
