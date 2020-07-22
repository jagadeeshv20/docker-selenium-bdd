pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				bat "docker pull jagadeeshv20/selenium-docker-bdd:latest"
			}
		}
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up"
			}
		}
	}
	post{
		always{
			bat "docker-compose down"
		}
	}
}