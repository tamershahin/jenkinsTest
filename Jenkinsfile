pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''wget https://s3.eu-west-2.amazonaws.com/tamer-resources/aws-s3.test.groovy
./gradlew clean :app:assemble 
'''
      }
    }
  }
}