pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Testing'
            junit 'target/**/*.xml'
          }
        }

        stage('integration test') {
          steps {
            echo 'Integration Test'
          }
        }

        stage('Performance Test') {
          steps {
            echo 'Performance Testing'
            timeout(time: 60) {
              echo 'Performance OO Performance'
            }

          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying'
        sh 'jenkins/deploy.sh'
      }
    }

  }
}