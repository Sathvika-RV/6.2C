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

        
        stage('Unit and Integration Tests') {
      steps {
        sh 'mvn test'
      }
    }
    stage('Code Analysis') {
      steps {
        withMaven(maven: 'Maven') {
          sh 'mvn checkstyle:checkstyle'
        }
      }
    }
    stage('Security Scan') {
      steps {
        sh 'mvn dependency-check:check'
      }
    }
    stage('Deploy to Staging') {
      steps {
        sh 'echo "Deploying to Staging"'
      }
    }
    stage('Integration Tests on Staging') {
      steps {
        sh 'echo "Running Integration Tests on Staging"'
      }
    }
    stage('Deploy to Production') {
      steps {
        sh 'echo "Deploying to Production"'
      }
    }
}
