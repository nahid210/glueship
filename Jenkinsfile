pipeline{
  agent {label "192.168.122.72"}
  
  stages {
    agetnt { 
      sh 'docker build -t nginxtest:v1.0.0 .'
     
    }
  }

	stage('deployment') {
               sh ' docker run -d --name glue-frontend --restart always -p $port:8080 test_backend:$BUILD_NUMBER_ENV'
              }
         } 
}
