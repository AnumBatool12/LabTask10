pipeline {
    agent any

    stages {
        stage('Step 1: Checkout'){
            steps {
                git https://github.com/ZoyaSumbul/Jenkins.git
            }
        }
        stage ('Step 2: Dependency Installation'){
            steps {
                sh 'npm install'
            }
        }
        stage ('Step 3: Build'){
            steps {
                sh 'npm run build'
            }
        }
        stage ('Step 4: Test'){
            steps {
                sh 'npm test'
            }
        }
        stage('Step 5: Containerization'){
            steps {
                sh 'docker build -d frontend-image'
                sh 'dcoker compose up'
            }
        } 
        stage('kill') {
            steps {
                sh "docker compose down"
            }
        }
    }
}
