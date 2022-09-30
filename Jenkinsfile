pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : '3.0.5') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : '3.0.5') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
          steps {
            script {
          deploy adapters: [tomcat9(credentialsId: 'd839536b-c6f6-4f3a-bf3f-6c38ed4fb6b3', path: '', url: 'http://3.238.147.187:8080/')], contextPath: null, war: ' **/*.war'
        }
            }
        }
    }
}
