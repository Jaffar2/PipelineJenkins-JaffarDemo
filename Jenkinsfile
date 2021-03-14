


pipeline {
    agent any
    stages {
        stage('Compile Stage') {
                steps {
                        echo 'Hi, this is Jaffar Maven Compile'
			
                }
        }
	    stage('Dev Stage'){
		    
		steps {
			echo 'Hi, this is Jaffar'
        }
	    }
        stage('Testing Stage') {
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
                        stage('Integration test') {
                        agent {
                                docker {
                                        reuseNode false
					image 'ubuntu'
                                        }
			}
				steps {
					echo 'Running the integration test..'
				}
                               
			}  }
        }
    }
}