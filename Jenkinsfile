pipeline {

	agent { 
	docker
	  {
		image 'maven:latest'
	  } 
	 }

	stages
	{
		stage('Build')
		{
			steps{
			  sh 'mvn --version'
			  echo "Build"
			}
		}
	
	    stage('Test')
		{
			steps{
			  echo "Test"
			}
		}
	    stage('Integration Test')
		{
			steps{
			  echo "Integration Test"
			}
		}
	}

	post
	{
	  always
	  {
		 echo 'I RUN ALWAYS'
	  }
	  success
	  {
		 echo 'I RUN succesfully'
	  }
	  failure
	  {
		 echo 'I failed to  RUN '
	  }
	}
		
}
