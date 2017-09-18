pipeline {
  agent any
  stages {
    stage('Download Deps') {
      steps {
        parallel(
          "Download Deps": {
            sh '''curl -o img.png https://s3.eu-west-2.amazonaws.com/tamer-resources/images/lo-zoo-di-105.png
            '''
            
          },
          "set up db": {
            sh 'echo "setting up db"'
            
          },
          "set up aws cli": {
            sh 'echo \'set up aws cli\''
            
          }
        )
      }
    }
    stage('copy files') {
      steps {
        sh '''ls -larth grails-app/assets/images/
                mv img.png grails-app/assets/images/grails_logo.png
                ls -larth grails-app/assets/images/
                '''
      }
    }
    stage('build') {
      steps {
        sh './gradlew clean :assemble'
      }
    }

    stage('Sanity check') {
                steps {
                    input "Does the staging environment look ok?"
                }
            }

  }
}