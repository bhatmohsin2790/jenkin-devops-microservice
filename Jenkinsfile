pipeline {

    agent any 
	//agent { 	docker	  {		image 'node:13.8'	  } 	 }

	environment 
	{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages
	{
		stage('Checkout')
		{
			steps{
			  sh 'mvn --version'
			  sh 'docker version'
			  echo "Build"
			  echo "PATH -$PATH"
			  echo "BUILD NUMBER $env.BUILD_NUMBER"
			  echo "BUILD ID $env.BUILD_ID"
			  echo "JOB NAME $env.JOB_NAME"
			  echo "BUILD TAG $env.BUILD_TAG"
			  echo "BUILD URL $env.BUILD_URL"



			}
		}
		stage('Compile')
		{
			steps
			{
				sh "mvn clean compile"
			}
		}
	    stage('Test')
		{
			steps{
			 sh "mvn test"
			}
		}
	    stage('Integration Test')
		{
			steps{
			  sh "mvn failsafe:integration-test failsafe:verify"
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
