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
            sh '''sh mvn clean package sonar:sonar -Dsonar.host.url=http://13.250.115.89:9000/ -Dsonar.login=1c96b646b7ce4a813dc88aa9670a98ecb776c460 -Dsonar.sources=. -Dsonar.tests=. -Dsonar.test.inclusions=**/test/java/servlet/createpage_junit.java -Dsonar.exclusions=**/test/java/servlet/createpage_junit.java
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