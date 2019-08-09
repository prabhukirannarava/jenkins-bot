pipeline {
  agent any
  stages {
    stage('unit tests') {
      steps {
        sh 'echo \'Running unit tests...\''
      }
    }
    stage('integration') {
      parallel {
        stage('integration') {
          steps {
            sh 'echo \'Running integration tests \''
          }
        }
        stage('ui') {
          steps {
            build(job: 'UI_tests', propagate: true, wait: true)
          }
        }
      }
    }
    stage('deploy') {
      steps {
        sh 'echo \'deploy\''
      }
    }
  }
}