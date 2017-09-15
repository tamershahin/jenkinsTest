pipeline {
  agent any
  stages {
    stage('Download Deps') {
      steps {
        parallel(
          "Download Deps": {
            sh '''curl -o img.jpg https://s3.eu-west-2.amazonaws.com/tamer-resources/images/lo-zoo-di-105.png
 

'''
            
          },
          "set up db": {
            sh 'echo "setting up db"'
            
          }
        )
      }
    }
    stage('Build app') {
      steps {
        parallel(
          "Build app": {
            sh './gradlew clean :assemble'
            
          },
          "add files": {
            sh 'mv img.jpg grails-app/assets/images/grails_logo.png '
            
          }
        )
      }
    }
  }
}