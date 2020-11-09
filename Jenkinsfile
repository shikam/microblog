pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
		cd /home/shai/Documents/backery/ex4/microblog 
		
		docker.build("microblog-image")
		docker.image("microblog-image").withRun('-p 8000:5000', '--name microblog-con -d')
            }
        }
        stage("Deploy to master"){
          when {
           branch 'master'
         }
         steps { 
            println 'Deploying to master'
          }
        }
        stage("Deploy to Production"){
          when {
           branch 'production'
         }
         steps { 
            println 'Deploying to production'
          }
        }
        stage("Deploy to development"){
          when {
            branch 'development'
          }
          steps {
            println 'Deploying to development'
          }
        }
    }
}
