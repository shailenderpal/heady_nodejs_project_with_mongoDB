pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
       
    }
    stages {
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
