pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
		 docker build -t microblog:latest .
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
