groovy
pipeline {
    agent any
    stages {
        stage('Run Script') {
            steps {
                sh 'script.sh'
            }
        }
    }
    post {
        always {
            emailext (
                subject: "Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' ${currentBuild.result}",
                body: '${SCRIPT,template="groovy-html.template"}',
                to: 'shanmathivlr03@gmail.com'
            )
        }
    }
}
