pipeline{
agent any

environment{
	DOCKERHUB_CREDENTIALS=credenetials('dockerhub')
}
stages{
	stage('init'){
	steps{

	sh 'docker rm -f $(docker ps -aq)'
}
}
	stage('build'){
	steps{
	sh './deploy.sh'
}
}
	
}
}



}
