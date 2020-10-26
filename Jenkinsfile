pipeline {
    agent any
    stages {
        stage('One') {
            steps {
                    echo 'Hi, testing stage one of pipeline'
        
            }
        }
	    stage('Two'){
		    
            steps {
                input('Do you want to proceed?')
            }
	    }
        stage('Three') {
                when {
                        not {
                                branch "master"
                        }
                }
                steps {
			        echo "Hello"
                }
        }
        stage('Four') {
            parallel {
                stage('Unit Test') {
                        steps{
                                echo "Running the unit test..."
                        }
                }
                stage('Deployment')  {
                    steps {
                        echo 'Ready for Deployment'
                    }
                                
                }  
            }
        }
    }
}
