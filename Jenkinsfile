pipeline {

	agent { 
	docker
	  {
		image 'maven:3.6.1'
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
