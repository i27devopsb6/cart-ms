pipeline {
    agent any 
    environment {
        DEPLOY_TO = 'production'
    }
    stages {
        stage ('DeployToDev') {
            steps {
                echo "Deploying to dev environment"
            }
        }
        stage ('ProdDeploy') {
            when {
                allOf {
                    branch 'production'
                    environment name: 'DEPLOY_TO', value: 'production'
                }
            }
            steps {
                echo "Deplying to production environment"
            }
        }
    }
}
