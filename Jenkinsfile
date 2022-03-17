pipeline {
    agent any
    stages {

        stage('Build') {
            steps {
                sh "mvn compile"
            }
        }
        stage('Test') {
            steps {
                sh "mvn test"
            }
            post {
                always {
                    junit '**/TEST*.xml'
                }
            }
        }
          stage('newman') {
            steps {
                sh 'newman run Postman_Labb_Collection_AnnChristinePhan_MT21.postman_collection.json --environment Postman_Labb_Environment_AnnChristinePhan_MT21.postman_environment.json --reporters junit'
            }
            post {
                always {
                        junit '**/*xml'
                 }
            }
        }
    }
}

