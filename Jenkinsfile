pipeline {
    agent any
    tools {
    maven 'Maven installation'
    }
    stages {
        stage('Build') {
            steps {
                echo "Build"
                sh 'mvn clean package -DSkipTests=true'
                archive 'target/*.jar'
                
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

        stage('Unit and Integration Tests') {
            tools {
                maven 'Maven installation'
            }
            steps {
                sh 'echo hello'
            }
        }
    }
}
