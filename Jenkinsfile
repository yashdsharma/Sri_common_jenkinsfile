pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                script{
                    snapshotSkipFlag = 'true'
                    echo "Checkout Stage"
                    branchName = "$BRANCH_NAME"
                    if (branchName.startsWith('ma')){
                        repos = ['main', 'mains', 'mainlands']
                        echo "Entering all main repos"
                        echo "Printing repos(2)"
                        rr = repos.get(2)
                        echo "$rr"
                    }
                    else if (branchName.startsWith('ya')){
                        echo "Entering yash branch"
                    }
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
                   // sh (returnStdout: true, script: """ C:/Users/ysharma/Desktop/script.sh""")
                   // assert response ==~ /.*200,.*/ : response
            }
            }
        }
            
    }
        
}
