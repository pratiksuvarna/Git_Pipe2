# Git_Pipe2
pipeline {	 
	agent any	 
    	stages {     	 
    	stage("Build") {          	 
            	steps {               	 
                	echo "Building the webapp with Maven"
          	 	build "BuildJob"
            	}     	 
        	}     	 
    	stage("Test") {          	 
        	steps {               	 
                	echo "Testing the webapp with JUnit"
			build "TestJob"
            	}     	 
        	}
	stage("Deploy") {          	 
        	steps {               	 
                	echo "Deploying Tomcat to AWS EC2 Instannce"
			build "Deployment"
            	}     	 
        	}	 
    	}
}
