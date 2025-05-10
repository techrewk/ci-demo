pipeline {
  agent any
  tools {
    maven 'M3'   // Add Maven in Jenkins global tools
    jdk 'JDK21'  // Add JDK in Jenkins global tools
  }

  stages {
    stage('Build') {
      steps {
        echo 'Building the project...'
        sh 'mvn clean install'
      }
    }

    stage('Test') {
      steps {
        echo 'Running tests...'
        sh 'mvn test'
        junit '**/target/surefire-reports/*.xml'
      }
    }
  }

  post {
    success {
      echo 'Build succeeded!'
    }
    failure {
      echo 'Build failed!'
    }
  }
}
