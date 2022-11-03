pipeline {
    agent any
    tools {
    maven '3.8.6'
    }

    stages {
        stage ('Compile Stage') {

            steps {
                
                    sh 'mvn compile'
                
            }
        }

        stage ('Package Stage') {

            steps {
                
                    sh 'mvn package'
                
            }
        }
        
        stage ('Deploy war to Tomcat') {
            
            steps {
                
                   deploy adapters: [tomcat7(url: 'http://192.168.1.121:8080/', credentialsId: 'f893bf1f-c498-41f8-b0c4-1b74dbd8c064')], war: 'target/*.war', contextPath: 'app'

            }
        }        
    }
}
