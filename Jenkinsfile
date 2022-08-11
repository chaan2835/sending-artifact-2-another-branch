pipeline { 
	agent any
		stages {
	
			stage ('build'){
					
							steps {
							
							sh 'mvn clean package'
					       			}
						}
	stage('listing-files-in-workspace') {
        steps {
		script {
		def pwd="${WORKSPACE}/target"
		sh "ls -R $pwd"
		// sh "ls -R ${WORKSPACE}" (to list all files in workspace)	
      		      		}
    			}
		}
		 stage('checking-branch') {
                        steps {
                                script {
                        if (env.BRANCH_NAME == 'develop' || 'main'){
                                echo "Runs on main (or) develop branch"
                                                      }
                        else {
                                echo "run on release branch"
                             }
                                }
                        }
                }

	}
}		
