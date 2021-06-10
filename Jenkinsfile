pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Testing'
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
        input(message: 'hi ! Are you sure for deployment?', id: 'id1', ok: 'Yes')
        echo 'Deploying'
        git(url: 'git@github.com:sundarsomasundaram/jenkins-microservice_ci-pipeline.git', branch: 'main')
      }
    }

  }
}