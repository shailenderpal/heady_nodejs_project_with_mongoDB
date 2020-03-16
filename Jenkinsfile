pipeline {
    agent any
    stages {
	
		stage('getting node image'){
            steps {
                sh "pwd"
                sh "ls -a"
                sh "docker build . -t nodejssamplewebapp:${env.BUILD_ID}"
            }
        }
        

    }
}
