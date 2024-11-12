pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/your-username/jenkins-website-ci.git', branch: 'main'
            }
        }
        stage('Build Website') {
            steps {
                bat './hello.bat'
            }
        }
        stage('HTML Validation') {
            steps {
                echo 'Running HTML Validation...'
                bat 'echo "HTML issues detected!"'
            }
        }
    }
}
