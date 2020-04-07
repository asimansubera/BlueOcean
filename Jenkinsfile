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
            sh '''sh \'mvn clean package sonar:sonar -Dsonar.host.url=http://3.1.202.152:9000/ -Dsonar.login=ff177383dda7da09c6364187a7d1b057c7fe64b7 -Dsonar.sources=. -Dsonar.tests=. -Dsonar.test.inclusions=**/test/java/servlet/createpage_junit.java -Dsonar.exclusions=**/test/java/servlet/createpage_junit.java\'
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