pipeline { 
    agent { dockerfile true }
    stages {
        stage('Build') { 
            steps {
	      script {
	       docker.build("microblog-image")
	       docker.image("microblog-image").withRun('-p 8000:5000', '--name microblog-con -d')
                  }
            }
	}
                        }
        post {
            success {
                echo "Pipeline successful"
        }
	    failure {
		 echo "The Pipeline failed :("
		    }
	}
	 }
