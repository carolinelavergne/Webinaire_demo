pipeline {
    agent any
    
    tools {nodejs "nodejs"}
    
    stages {
        stage("Newman package installation") {
            steps {
                sh 'npm install -g newman'
            }
        }
        stage("Run newman") {
            steps {
                script {
                    try {
                        sh 'newman run Demo.postman_collection.json -e ProdWebinaire.postman_environment.json -r junit,cli --reporter-junit-export newman.xml'
						currentBuild.result = 'SUCCESS'
                    } catch (Exception ex) {
                        currentBuild.result = 'FAILURE'
                    }
                    junit 'newman.xml'
                }
            }
        }
    }
}