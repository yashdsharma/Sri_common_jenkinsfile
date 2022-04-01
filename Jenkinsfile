pipeline {
    agent any
    parameters {
        string(name: 'target', defaultValue: "$BRANCH_NAME", description: 'Target deployment env.' )
    }
    stages {
        stage('checkout') {
            steps {
                script{
                echo "Checkout"
                branchName = "${params.target}"
                echo "${branchName}"
                }
            }
        }
        stage('deploy'){
            steps {
                script{
            echo "This is deploy"
            }
            }
        }
    post {
        always{
            echo "Always"
        }
        success{
            echo "Successffff"
        }
        failure{
            echo "Failureeeeeee"
        }
    }
            
    }
        
}
