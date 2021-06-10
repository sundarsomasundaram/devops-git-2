pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
        sh 'jenkins/build.sh'
        node(label: 'node1')
        tool(name: 'maven', type: 'build')
        dockerNode(image: 'maven:3.3-jdk-8')
      }
    }

    stage('Test') {
      steps {
        echo 'Testing'
        sh 'jenkins/test-all.sh'
        junit 'target/**/*.xml'
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