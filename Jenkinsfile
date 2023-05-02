pipeline {
    agent any
    tools {
    maven '3.8.6'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building artifacts using Maven automation tool"
                bat "mvn --version"
                               
            }
        }

        
        stage('Unit and Integration Tests') {
      steps {
        //sh 'mvn test'
          echo "Doing Unit and integration tests using Test Maven - JUnit"
      }
          post {
              always {
             emailext body: "Unit and Integration Tests results attached\n\n", 
             subject: "Unit and Integration Tests Results: ${currentBuild.result}", 
             to: "sathvikarv97@gmail.com",
             attachLog: true
             
              }
     }
      
    }
    stage('Code Analysis') {
      steps {
        echo "Analysing code using Maven checkstyle"
      }
    }
    stage('Security Scan') {
      steps {
       // sh 'mvn dependency-check:check'
          echo "Security scan using SAST- Sonarcube or Maven Spotbugs"
       
      }
    
         post {
              always {
             emailext body: "Security Scan results attached\n\n", 
             subject: "Security Scan Results: ${currentBuild.result}", 
             to: "sathvikarv97@gmail.com",
             attachLog: true
             
              }
     }
}
    stage('Deploy to Staging') {
      steps {
        echo "Deploying to Staging server that is present on AWS cloud. Its an EC2 instance"
      }
    }
    stage('Integration Tests on Staging') {
      steps {
        echo "Running Integration Tests on Staging usinf TestNG"
      }
        post {
              always {
             emailext body: "Integration Tests results attached\n\n", 
             subject: "Integration Tests on Staging Results: ${currentBuild.result}", 
             to: "sathvikarv97@gmail.com",
             attachLog: true
             
              }
     }
      
    }
    stage('Deploy to Production') {
      steps {
        echo "Deploying to Production server that is present on AWS cloud. Its an EC2 instance in different account than staging server"
      }
    }
}
}
