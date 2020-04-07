pipeline {
  agent any
  stages {
    stage('Static Code Test') {
      parallel {
        stage('Static Code Test') {
          steps {
            echo 'Before Sonar Test'
          }
        }

        stage('Sonar Test') {
          steps {
            sh '''sh \'mvn sonar:sonar -Dsonar.host.url=http://13.250.115.89:9000/ -Dlicense.skip=true\'
'''
          }
        }

        stage('Print Tester Name') {
          steps {
            echo 'The tester is ${TESTER}'
          }
        }

      }
    }

    stage('Print Message') {
      steps {
        echo 'This is build number ${BUILD_ID}'
      }
    }

  }
}