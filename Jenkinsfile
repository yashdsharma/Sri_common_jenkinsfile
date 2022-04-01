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
                    branchName = 'mxuat2'
                    testing = true
                    echo "${branchName}"
                    
                    
                    
                    repos.each { repo ->
                        println it
                        
                    dir('cd-pipeline') {
                        echo "Inside cd-pipeline"
                    	checkout([
                        	$class: 'GitSCM',
                      		branches: [[name: '*/yash']],
                      		userRemoteConfigs: [[
                            	url: 'https://github.com/yashdsharma/Sri_common_jenkinsfile.git'
                            ]]
                        ])
                    }
                    }
                }
            }
        }
        stage('deploy'){
            steps {
                script{
            echo "Deployment Stage"
                    assert response ==~ /.*200,.*/ : response
            }
            }
        }
            
    }
        
}
