pipeline {
    agent any
    // Global env section, can be used by all stages
    environment {
        course = "Docker and K8S"
        name = "Siva"
    }
    stages {
        stage ('Build') {
            // this is specifc to this stage, and cant be used by others
            environment {
                cloud = "GCP"
            }
            steps {
                echo "Welcome ${name}"\
                echo "You enrolled for ${course}"
                echo "You are certified in ${cloud}"
            }
        }
    }
}


// ${name}
// ${env.name}
// ${params.name}
