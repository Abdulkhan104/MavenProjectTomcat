// pipeline {
//     agent any

//     stages {
//         stage('clone') {
//             steps {
//                git branch: 'main', url: 'https://github.com/Abdulkhan104/MavenProjectTomcat.git'
//             }
//         }
//         stage('build') {
//             steps {
//                 sh 'mvn package'
//             }
//         }
//         stage('AutomationWithTOMCAT') {
//             steps {
//                 deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat-1', path: '', url: 'http://54.234.153.236:8081/')], contextPath: null, war: '**/*war'
//             }
//         }
//     }
// }
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
        stage('DeployToTomcat') {
            steps {
                deploy adapters: [
                    tomcat9(
                        credentialsId: 'tomcat-1', 
                        path: '', 
                        url: 'http://98.81.82.64:8081/'
                    )
                ], 
                contextPath: 'http://98.81.82.64:8081/webapp/', 
                war: 'webapp/target/webapp.war'
            }
        }
    }
}
