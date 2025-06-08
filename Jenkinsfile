pipeline{
  agent any

  tools{
    gradle 'Gradle'
    jdk 'JDK'
  }

  stages{
    stage('check'){
      steps{
        git branch:'master',url:'https://github.com/shar4440/gradle17.git'
      }
    }

    stage('build'){
      steps{
        sh 'gradle build'
      }
    }

    stage('test'){
      steps{
        sh 'gradle test'
      }
    }

    stage('run'){
    steps{
      sh 'gradle run'
    }
  }
}

post{
  success{
    echo 'yes'
  }
  failure{
    echo 'noooooo'
  }
}
}
