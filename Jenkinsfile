pipeline {
    agent any
    tools {
    maven '3.8.6'
    }
    stages {
        stage('Building') {
            steps {
                echo "Build"
                bat "mvn --version"
                //sh 'mvn clean package -DSkipTests=true'
                //archive 'target/*.jar'
                
            }
                //post {
                   // always {
                         // send email notification with security scan results
              //  mail body: "Build results attached", 
              //  subject: "Security Scan Results: ${currentBuild.result}", 
             //   to: "sathvikarv97@gmail.com"
             
//  }
//}
            
        }

 
      stage('Test Maven - JUnit') {
            steps {
              bat "mvn test"
            }
            post{
              always{
                junit 'target/surefire-reports/*.xml'
              }
            }
        }
        
        
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                sh 'echo hello'
            }
        }
    }
}
