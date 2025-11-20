pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'chmod +x test.sh'
                sh './test.sh'
            }
        }
    }

    post {
        always {
            emailext (
                to: 'bhanusivaprakashreddy1997@gmail.com',
                subject: "Jenkins Build Result: ${currentBuild.currentResult}",
                body: "Build completed.\nCheck Jenkins console for full logs."
            )
        }
    }
}

