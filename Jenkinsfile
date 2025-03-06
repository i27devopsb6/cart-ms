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
                anyOf {
                    branch 'production'
                    environment name: 'DEPLOY_TO', value: 'productioenv'
                }
            }
            steps {
                echo "Deplying to production environment"
            }
        }
    }
}
