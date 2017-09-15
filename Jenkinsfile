pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''curl https://s3.eu-west-2.amazonaws.com/tamer-resources/images/lo-zoo-di-105.png
./gradlew clean :app:assemble 
'''
      }
    }
  }
}