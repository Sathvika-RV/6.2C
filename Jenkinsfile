pipeline {
    agent any
    tools {
    maven '3.8.6'
    }
    stages {
        stage('Build') {
            steps {
                echo "Build"
                bat "mvn --version"
                               
            }
        }

        
        stage('Unit and Integration Tests') {
      steps {
        //sh 'mvn test'
          echo "Doing Unit and integration tests"
      }
    }
    stage('Code Analysis') {
      steps {
        echo "Analysing code using xxx"
      }
    }
    stage('Security Scan') {
      steps {
       // sh 'mvn dependency-check:check'
          echo "Security scan using SAST- Sonarcube"
       
      }
    
         post {
              always {
             emailext body: "Build Scan results attached\n\n", 
             subject: "Test Results: ${currentBuild.result}", 
             to: "sathvikarv97@gmail.com",
             attachLog: true,
             
              }
     }
}
    stage('Deploy to Staging') {
      steps {
        echo "Deploying to Staging"
      }
    }
    stage('Integration Tests on Staging') {
      steps {
        echo "Running Integration Tests on Staging"
      }
    }
    stage('Deploy to Production') {
      steps {
        echo "Deploying to Production"
      }
    }
}
}
