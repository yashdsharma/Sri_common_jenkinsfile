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
                if (branchName.startsWith('ma')){
                    repos = ['main', 'mains']
                    echo "Entering all main repos"
                }
                else if (branchName.startsWith('ya')){
                    echo "Entering yash branch"
                }
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
