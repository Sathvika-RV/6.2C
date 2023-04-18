pipeline {
    agent any
    tools {
    maven 'Maven'
    }
    stages {
        stage('Build') {
            steps {
                echo "Build"
                sh 'mvn clean package'
                
            }
                post {
                    always {
                         // send email notification with security scan results
                mail body: "Build results attached", 
                subject: "Security Scan Results: ${currentBuild.result}", 
                to: "sathvikarv97@gmail.com"
             
  }
}
            
        }
    }
}
