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
                        repos = ['Srikanth_repo31', 'Srikanth_repo21', 'Srikanth_repo12']
                        //echo "Entering all main repos"
                       // echo "Printing repos(2)"
                        //rr = repos.get(2)
                        //echo "$rr"
                    }
                    else if (branchName.startsWith('ya')){
                        echo "Entering yash branch"
                    }
                    else if (branchName.startsWith('AA')){
                        repos = ['Srikanth_repo11']
                    }
                    else if (branchName.startsWith('EE')){
                        repos = ['Srikanth_repo21']
                    }
                    
                    
                 repos.each { repo ->
                        dir(repo) {
                            checkout([
                                $class: 'GitSCM',
                                branches: [[name: branchName]],
                                userRemoteConfigs: [[ credentialsId: '',
                                url: "https://github.com/yashdsharma/${repo}.git"]]
                            ])
                        }
                    }
             '''   repos.each { repo ->
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
                    }'''
                }
            }
        }
        stage('deploy'){
            steps {
                script{
            echo "Deployment Stage"
                    sh (returnStdout: true, script: """ python main.py""")
                   // assert response ==~ /.*200,.*/ : response
            }
            }
        }
            
    }
        
}
