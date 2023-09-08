pipeline{
	agent any

	tools {
		maven 'maven-3.9'
	}

	stages{
		stage('Checkout Code'){
			steps{
				checkout poll: false, scm: scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/soniashaji/jenkins_pipeline_springboot_demo.git']])
			}
		}

		stage('Build'){
			steps{
				echo "Build Stage"
				sh 'mvn compile'
			}
		}

		stage('Test'){
			steps{
				echo "Test Stage"
				sh 'mvn test'
			}	
		}

		stage('Deploy'){
			steps{
				echo "Deploy Stage"
				sh 'mvn install'
			}
		}

	}

}
