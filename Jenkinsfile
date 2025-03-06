// pipleine e2e
pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                echo "Building the project"
            }
        }
        stage ('CodeAnalysis') {
            steps {
                echo "Running code analysis"
            }
        }   
        stage ('DockerBuildnPush') {
            steps {
                echo "Building and pushing docker image"
            }
        }
        stage ('DeployToDev') {
            steps {
                echo "Deploying to dev environment"
            }
        }
        stage ('DeployToTest') {
            steps {
                echo "Deploying to test environment"
            }
        }
        stage ('DeployToStage') {
            when {
                branch 'release-*'
            }
            steps {
                echo "Deploying to stage environment"
            }
        }
        stage ('DeployToProd') {
            when {
                // vx.x.x
                // v1.2.3 is correct
                // v.1.2.3 is wrong
                tag pattern: "v\\d{1,2}.\\d{1,2}.\\d{1,2}" , comparator: "REGEXP"
            }
            steps {
                echo "Deploying to prod environment"
            }
        }
    }
}
