pipeline{
	agent any
	tools {nodejs "nodejs"}
	stages {
		stage ("Newman install") {
			steps{
				sh 'npm install -g newman'
			}
		}
		stage ("Test execution") {
			steps {				
				steps {​
	                script {​
	                    try {​
	                        sh 'newman run Demo.postman_collection.json -e ProdWebinaire.postman_environment.json -r junit,cli --reporter-junit-export newman.xml'​
	                        currentBuild.result = 'SUCCESS'​
	                    } catch (Exception ex) {​
	                        currentBuild.result = 'FAILURE'​
	                    }​
	                    junit 'newman.xml'​
	                }​
	            }​	
			}
		}
	}
}