node {
    stage('SCM Checkout'){
       
       git (credentialsId: 'GithubCreds', url: 'https://github.com/pm059321/Build-CICD-pipleine-using-Dockerfile',branch: 'main')
	}
	stage('Maven Clean'){
	    def mvnHome = tool name: 'maven 3.8.6', type: 'maven'
	    bat 'mvn clean'
	}
	stage('Pulling the docker image'){
	            echo 'Running the docker compose'
                //cd /root/simpledocker
                //sh 'docker pull jenkins/jenkins:2.320'
        }
    stage('Running the Docker Compose '){
                echo 'Running the docker compose'
                //cd /root/simpledocker
                //sh 'docker-compose -f docker-compose.yml up -d'
        }
}
