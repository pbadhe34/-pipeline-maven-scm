 pipeline {
    agent any

    tools {         
        maven "maven3.5"
    }

    stages {
        stage('Build') {
            steps {                 
                
                bat "rm -r -f ./Maven-Spring-App"
                
                git url: 'git://github.com/pbadhe34/Maven-Spring-App.git', branch: 'main'               

              
                // To run Maven on a Windows agent, use
                 bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            post {                
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    //archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}

 