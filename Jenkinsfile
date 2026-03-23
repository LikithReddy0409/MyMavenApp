pipeline{
	agent any
	
	tools{
		maven 'Maven'
	}
	
	stages{
		stage('Checkout'){
			steps{
				git branch: 'main', url: 'https://github.com/LikithReddy0409/MyMavenApp.git'
			}
		}
		stage('Build'){
			steps{
				sh 'mvn clean package'
			}
		}
		stage('Test'){
			steps{
				sh 'mvn test'
			}
		}
		stage('Run Application'){
			steps{
				sh 'java -jar target/MavenApp_Test-1.0-SNAPSHOT.jar'
			}
		}
	}
	post{
		success{
			echo 'Build and deployment successfull'
		}
		failure{
			echo 'Build Failed'
		}
	}
}
