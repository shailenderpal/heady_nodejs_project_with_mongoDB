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
        stage('Build Application') {
            steps {
               sh 'npm install'
            }
            post {
                success {
                    echo "Now Archiving the Artifacts...."
                    archiveArtifacts artifacts: '**/*.json'
                }
            }
        }

        stage('Create nginx Docker Image'){
            steps {
                sh "pwd"
                sh "ls -a"
                sh "docker build . -t nginxsamplewebapp:${env.BUILD_ID}"
            }
        }

    }
}
