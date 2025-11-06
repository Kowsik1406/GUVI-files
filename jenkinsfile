pipeline {
    agent any
    stages {
        stage ('clone repo') {
            steps {
                git branch : 'main' , url: 'https://github.com/Kowsik1406/GUVI-files.git'
            }
        }
        stage ('execute script file') {
            steps {
                sh 'chmod +x hello.sh'
                sh './hello.sh'
            }
        }
    }
    post {
        always {
            emailtext(
                to: 'kowsikvigrams2@gmail.com'
                subject: "Jenkins Build: ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                body: """Build URL: ${env.BUILD_URL}
Result: ${currentBuild.currentResult}
"""
            )
        }
    }
}
