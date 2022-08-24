pipeline {
	agent any 
	stages {
    stage(‘Build’) {
	steps {
		sh "rm -rf nginx"
        sh "git clone https://github.com/petejades/nginx.git"
	}
	}
	stage (‘Test’) {
	steps {
		sh "cd nginx && ls && git branch"
	
	}
	}
    stage (‘Package’) {
	steps {
		sh "cd nginx && docker build -t webserver  ."

	}
	}
        stage (‘deploy’) {
	steps {
		sh "cd nginx && docker stop webserver || true && docker rm webserver || true && docker run -d -p 80:80 --name webserver webserver:latest"

	}
	}
}
}



