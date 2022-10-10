pipeline {
    agent any
    tools {
    maven 'mvncfg'
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
                
                   deploy adapters: [tomcat7(url: 'http://192.168.1.170:8080/', credentialsId: '3adce66e-bedd-441f-aeca-661ce6a11bbc')], war: 'target/*.war', contextPath: 'app007'

            }
        }        
    }
}
