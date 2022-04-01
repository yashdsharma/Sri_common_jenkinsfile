pipeline {
    agent any
    parameters {
        string(name: 'target', defaultValue: "$BRANCH_NAME", description: 'Target deployment env.' )
    }
    stages {
        stage('checkout') {
            steps {
                echo "Checkout"
                branchName = "${params.target}"
                echo "${beanchName}"
                }
        }
        stage('deploy'){
            steps {
            echo "This is deploy"
            }
        }
    post {
        always{
            //
        }
    }
            
    }
        
}
