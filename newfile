pipeline {
    agent any 
    stages {
        stage ('Build') {
            steps {
                echo "********** Building the application *******************"
                sh 'mvn package'
            }
        }
        stage ('Sonar') {
            steps {
                echo "******************* Scanning the application ****************"
            }
        }
        stage ('Docker') {
            steps {
                echo "***************Building the docker image *************************"
            }
        }
        stage ('K8SDeploy') {
            steps {
                echo "******************* Deploying using k8s *************************"
            }
        }
    }
}
