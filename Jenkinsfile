pipeline {
	agent any
	tools {
		jdk 'localJDK'
		maven 'localMaven'
	}
	stages {
		stage("Maven-Build"){
			steps {
				sh 'mvn -Dmaven.test.skip=true install'
			}
		}
		stage ("Docker Login") {
			steps {
				sh 'docker login -u satyendrasingh -p Password@123'
			}
		}
		stage("Docker-Build"){
			steps {
				sh "docker build -t search:${env.BUILD_ID} search/"
			}
		}
	}
}
