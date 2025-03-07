pipeline {
    agent any 
    parameters {
        choice(name: 'buildOnly',
            choices: 'yes\no',
            description: "This will only build the application"
        )
        choice(name: 'dockerPush',
            choices: 'yes\no',
            description: "This will build and push to docker repo"
        )
        choice(name: 'deployToDev',
            choices: 'yes\no',
            description: "This will deploy the app to dev env"
        )
        choice(name: 'deployToTest',
            choices: 'yes\no',
            description: "This will deploy the app to test env"
        )
        choice(name: 'deployToStage',
            choices: 'yes\no',
            description: "This will deploy the app to stage env"
        )
        choice(name: 'deployToProd',
            choices: 'yes\no',
            description: "This will deploy the app to prod env"
        )   
        choice(name: scanOnly,
            choices: 'yes\no',
            description: "This will only run the code analysis"
        )

    stages {
        stage ('Build') {
            when {
                expression {
                   params.buildOnly == 'yes'
                }
            }
            steps {
                echo "Building the project"
            }
        }
        stage ('CodeAnalysis') {
            when {
                expression {
                   params.scanOnly == 'yes'
                }
            }
            steps {
                echo "Running code analysis"
            }
        }   
        stage ('DockerBuildnPush') {
            when {
                expression {
                   params.dockerPush == 'yes'
                }
            }
            steps {
                echo "Building and pushing docker image"
            }
        }
        stage ('DeployToDev') {
            when {
                expression {
                   params.deployToDev == 'yes'
                }
            }
            steps {
                echo "Deploying to dev environment"
            }
        }
        stage ('DeployToTest') {
            when {
                expression {
                   params.deployToTest == 'yes'
                }
            }
            steps {
                echo "Deploying to test environment"
            }
        }
        stage ('DeployToStage') {
            when {
                expression {
                   params.deployToStage == 'yes'
                }
            }
            steps {
                echo "Deploying to stage environment"
            }
        }
        stage ('DeployToProd') {
            when {
                allOf {
                    anyOf {
                        expression {
                            params.deployToProd == 'yes'
                        }
                        // write one more logic
                    }
                    anyOf {
                        branch 'production'
                    }
                }
            }
            options {
                timout (time: 300, unit: 'SECONDS')
            }
            input {
                message "Doing prod Deployments ??????"
                ok 'yes'
                submitter 'i27academy,krishdev'
            }
            steps {
                echo "Deploying to prod environment"
            }
        }
    }
    }
}
