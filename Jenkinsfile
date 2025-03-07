pipeline {
    agent any 
    stages {
        stage ('Build') {
            steps {
                echo "Building the application"
            }
        }
    }
    post {
        // Only run this, when the current pipeline or a specfic stage has a success status
        success {
            echo "Post ===================> Success is triggered "
        }
        // Only run when the pipelien or stage is haing a failure status
        failure {
            echo "Post ===================> Failure is triggered "
        }
        // This will run irrespctive of failure or success...meaning everytime
        always {
            echo "Post ===================> Always is triggered "
        }
    }
}
