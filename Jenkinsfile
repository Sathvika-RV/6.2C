pipeline {
    agent any
    tools {
    maven 'Maven 3.8.6'
    }
    stages {
        stage('Building') {
            steps {
                echo "Build"
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

        stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar' 
            }  
       }
      stage('Test Maven - JUnit') {
            steps {
              sh "mvn test"
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
