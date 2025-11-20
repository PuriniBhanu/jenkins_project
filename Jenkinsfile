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
            subject: "Build Result: ${currentBuild.currentResult}",
            body: """<pre>
${BUILD_LOG, maxLines=-1}
</pre>"""
        )
    }

}
}
