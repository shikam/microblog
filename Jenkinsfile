pipeline { 
    agent { dockerfile true }
    stages {

        stage('Build') { 
            steps {
			echo 'Start build'
                	sh 'docker build -t microblog:latest .'
			sh 'docker run --name microblog -d -p 8001:5000 --rm microblog:latest'
			  
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
