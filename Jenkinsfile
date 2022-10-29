pipeline {
    agent {
        label 'glueship'
    }

    stages {
	
		stage('Docker image Build') {
            steps {
            	sh """
                   git clone https://github.com/nahid210/glueship
            	"""
            }
        }
        stage('Docker image Build') {
            steps {
            	sh """
                    docker build -t nginxtest:v1.00 .
            	"""
            }
        }

        stage('Docker container creation') {
            steps { 
                sh """
            	    echo "succeessfully install"
                """
            }
        }
    }

    post {
        success {
            script {
				sh """
					echo "This is success"
				"""

            }
        }
        failure {
            script {
				sh """
					echo "This is failed"
				"""
            }
        }

    }
}