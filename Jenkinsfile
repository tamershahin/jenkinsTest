pipeline {
  agent any
  stages {
    stage('Download Deps') {
      steps {
        sh '''curl -o img.jpg https://s3.eu-west-2.amazonaws.com/tamer-resources/images/lo-zoo-di-105.png
 

'''
      }
    }
    stage('Build app') {
      steps {
        sh './gradlew clean :assemble'
      }
    }
  }
}