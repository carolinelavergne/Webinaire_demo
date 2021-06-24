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
				sh 'newman run Demo.postman_collection.json -e ProdWebinaire.postman_environment.json'
			}
		}
	}
}