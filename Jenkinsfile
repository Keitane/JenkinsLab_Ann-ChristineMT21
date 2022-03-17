pipeline {
    agent any
    stages {

        stage('Build') {
            steps {
                bat "mvn compile"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test"
            }
            post {
                always {
                    junit '**/TEST*.xml'
                }
            }
        }
          stage('newman') {
            steps {
                sh 'newman run Postman_Labb_Collection(Ann-ChristinePhan_MT21).postman_collection.json --environment Postman_Labb_Environment(Ann-ChristinePhan_MT21).postman_environment.json --reporters junit'
            }
            post {
                always {
                        junit '**/*xml'
                 }
            }
        }
    }
}

