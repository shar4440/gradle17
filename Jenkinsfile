pipeline {
  agent any

  tools {
    gradle 'Gradle'   // Make sure this matches the name configured in Jenkins Global Tools
    jdk 'JDK'         // Ensure this JDK version exists in Jenkins Global Tools
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'master', url: 'https://github.com/shar4440/gradle17.git'
      }
    }

    stage('Build') {
      steps {
        sh './gradlew clean build' // Prefer wrapper if available, else use 'gradle build'
      }
    }

    stage('Test') {
      steps {
        sh './gradlew test'
      }
    }

    stage('Run') {
      steps {
        sh './gradlew run'
      }
    }
  }

  post {
    success {
      echo '✅ Build succeeded!'
    }
    failure {
      echo '❌ Build failed.'
    }
  }
}
