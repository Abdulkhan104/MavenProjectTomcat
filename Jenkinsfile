pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
               git branch: 'main', url: 'https://github.com/Abdulkhan104/MavenProjectTomcat.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('AutomationWithTOMCAT') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat-1', path: '', url: 'http://54.234.153.236:8081/')], contextPath: null, war: '**/*war'
            }
        }
    }
}
