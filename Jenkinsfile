pipeline{
  agent {label "192.168.122.72"}
  
  stages {
    agetnt { 
   sh 
    docker build -t nginxtest:v1.0.0 .
     
    }
  }

	stage('deployment') {
               sh 
            		if [ ! -z  "\$(docker ps -a -q -f name=glue-frontend)" ];then
            		  echo "Found running container"
            		  docker container stop glue-frontend
            		  docker container rm glue-frontend
            		  docker run -d --name glue-frontend --restart always -p $port:8089 test_backend:$BUILD_NUMBER_ENV
            		else
		          docker run -d --name glue-frontend --restart always -p $port:8080 test_backend:$BUILD_NUMBER_ENV
            		fi
            	
                         }
         } 
   }
}
