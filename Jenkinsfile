node {
	def app

	stage('Clone'){
		checkout csm
	}
	stage('Build Image'){
		app = docker.build("ahmed/nginx")
	}
	stage('Test Image'){
		  docker.image('ahmed/nginx').withRun('-p 8081:80'){
		  	c-> 
		  	sh 'docker ps'
		  	sh 'curl localhost:8081'
		  }
	}
}