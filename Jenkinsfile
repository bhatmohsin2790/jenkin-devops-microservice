pipeline {

    agent any 
	//agent { 	docker	  {		image 'node:13.8'	  } 	 }

	stages
	{
		stage('Build')
		{
			steps{
			  //sh 'node --version'
			  echo "Build"
			  echo "PATH -$PATH"
			  echo "BUILD NUMBER $env.BUILD_NUMBER"
			  echo "BUILD ID $env.BUILD_ID"
			  echo "JOB NAME $env.JOB_NAME"
			  echo "BUILD TAG $env.BUILD_TAG"
			  echo "BUILD URL $env.BUILD_URL"



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
