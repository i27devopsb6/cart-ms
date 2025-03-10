pipeline {
    agent any 
    stages {
        stage ('Build') {
            steps {
                echo "Building the project"
            }
        }
    }
    post {
        always {
            script {
                def subject = "Job Status is: ${currentBuild.currentResult}"
                def body = "Build Number is: ${currentBuild.number}\n" + "Status is: ${currentBuild.currentResult}\n" + "Job URL: ${env.BUILD_URL}"
                mail to 'i27k8s10@gmail.com',
                    subject: subject,
                    body: body
            }
        }
    }
}
