pipeline {
    agent any
    parameters {
        string(name: 'target', defaultValue: "$BRANCH_NAME", description: 'Target deployment env.' )
        string(name: 'snapshotSkipFlag', defaultValue: '', description: 'Skip snapshot')
    }
    stages {
        stage('checkout') {
            steps {
                script{
                    echo "Checkout Stage"
                    branchName = "${params.target}"
                    if (branchName.startsWith('ma')){
                        repos = ['main', 'mains']
                        echo "Entering all main repos"
                    }
                    else if (branchName.startsWith('ya')){
                        echo "Entering yash branch"
                    }
                    branchName = 'mxuat2
                    echo "${branchName}"
                    
                    
                    repos.each { repo ->
                        println it
                    }
                }
            }
        }
        stage('deploy'){
            steps {
                script{
            echo "Deployment Stage"
            }
            }
        }
            
    }
        
}
