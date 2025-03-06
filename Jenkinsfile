pipeline {
    agent any 
    stages {
        stage ('Build') {
            steps {
                echo "Building the project"
            }
        }
        stage ("ParallelStageScans"){
            parallel {
                stage ('CodeAnalysis') {
                    steps {
                        echo "Running code analysis"
                        sleep 10    
                    }
                }
                stage ('SecurityScan') {
                    steps {
                        echo "Running security scan"
                        sleep 10
                    }
                }
                stage ('PerformanceTest') {
                    steps {
                        echo "Running performance test"
                        sleep 10
                    }
                }
            }
        }
    }
}
