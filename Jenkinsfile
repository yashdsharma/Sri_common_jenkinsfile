pipeline {
    agent any
    parameters {
        string(name: 'target', defaultValue: "$BRANCH_NAME", description: 'Target deployment env.' )
        choice(name: 'VERSION', choices: ['1.1', '2.2', '3.3'], description: '')
    }
    stages {
        stage('checkout') {
            steps {
                script {
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
            
    }
        
}
