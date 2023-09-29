pipeline{
agent any

environment{
	DOCKERHUB_CREDENTIALS=credentials('dockerhub')
}
stages{
	stage('init'){
	steps{

	sh 'docker rm -f $(docker ps -aq)'
}
}
	stage('build'){
	steps{
	sh 'chmod +x deploy.sh'
	sh './deploy.sh'
}
}
   stage('push'){
            steps{
                sh 'echo \$DOCKERHUB_CREDENTIALS_PSW | docker login -u \$DOCKERHUB_CREDENTIALS_USR --password-stdin'
                sh 'docker tag trio-task-mysql:5.7 semery1/sql1:latest'
		sh 'docker tag trio-task-flask-app:latest semery1/flask-app1:latest'
                sh 'docker push semery1/sql1:latest'
		sh 'docker push semery1/flask-app1:latest'
		
        }
    }	
}
}
