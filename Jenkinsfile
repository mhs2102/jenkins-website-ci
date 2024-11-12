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
                    // Add all changed files
                    sh 'git add .'
                    
                    // Commit changes with a message
                    sh 'git commit -m "Automated commit after build" || echo "No changes to commit"'
                    
                    // Push changes to the repository
                    sh 'git push origin main'
                }
            }
        }
    }
}
