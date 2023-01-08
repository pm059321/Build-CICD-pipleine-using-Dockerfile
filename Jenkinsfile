node {
   stage('SCM Checkout'){
        git (credentialsId: 'GithubCreds', url: 'https://github.com/pm059321/Build-CICD-pipleine-using-Dockerfile.git)
	}
     stage('Maven Clean'){
	    def mvnHome = tool name: 'maven 3.8.6', type: 'maven'
	    bat 'mvn clean'
	}	

      stage('Pulling the images and config Docker API remote'){
	        def dockerRun = 'docker run -p 8080:8080 -p 50000:50000 -v /root/jenkins:/var/jenkins_home jenkins/jenkins:2.320'
	        sshagent(['AWSUbuntucred']) {    
		    sh "ssh -o StrictHostKeyChecking=no ubuntu@172.31.23.43 ${dockerRun}"
		}
	        echo 'Pulling the docker images'
	        cd /root/Build-CICD-pipleine-using-Dockerfile
                sh 'docker pull jenkins/jenkins:2.320
                sh 'docker pull jenkins/slave'
	        
	        echo 'Configuring Docker API remote'
	        sh 'docker run -p 3375:2375 -v /var/run/docker.sock:/var/run/docker.sock -d shipyard/docker-proxy'
        }
        stage('Installing the docker compose and Running the Docker Compose'){
                echo 'Installing the docker compose'
		//sh 'curl -SL https://github.com/docker/compose/releases/download/v2.14.2/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose'
                //sh 'sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose'
                //sh 'sudo ln -s /usr/local/java/bin/jav /usr/bin/java'
                //sh 'sudo chmod +x /usr/local/bin/docker-compose'
				
                echo 'Running the Docker compose' 
                //cd /root/jenkins-master-slave-achitecture
                //sh 'docker-compose -f docker-compose.yml up -d'
        }
}
