pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Running unit tests..."
                post {
                    always {
                         // send email notification with security scan results
                emailext body: "Security Scan results attached", 
                subject: "Security Scan Results: ${currentBuild.result}", 
                to: "sathvikarv97@gmail.com"
             
  }
}
            }
        }
    }
}
