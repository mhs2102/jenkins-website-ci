pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/your-username/jenkins-website-ci.git'
            }
        }

        stage('Build Website') {
            steps {
                sh './hello.sh'
            }
        }

        stage('HTML Validation') {
            steps {
                echo 'Running HTML Validation...'
                sh 'tidy -q -e index.html || echo "HTML issues detected!"'
            }
        }

        stage('Commit Changes') {
            steps {
                script {
                    sh '''
                    git config user.name "Jenkins CI"
                    git config user.email "jenkins@example.com"
                    git add .
                    git commit -m "Automated commit after build"
                    git push origin main
                    '''
                }
            }
        }
    }
}
