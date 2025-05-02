pipeline {
    agent any

    tools {
        nodejs "NodeJS_18" 
    }

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'https://github.com/samarthVidealpha/test-jenkins.git', branch: 'master'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Archive Build') {
            steps {
                archiveArtifacts artifacts: 'build/**', fingerprint: true
            }
        }
    }
}
