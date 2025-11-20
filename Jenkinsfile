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
        emailext(
            to: 'bhanusivaprakashreddy1997@gmail.com',
            subject: "Job: ${env.JOB_NAME} #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
            mimeType: 'text/html',
            body: '''<h3>Build Result: ${currentBuild.currentResult}</h3>
<pre>
${BUILD_LOG, maxLines=-1}
</pre>'''
        )
    }
}
}
