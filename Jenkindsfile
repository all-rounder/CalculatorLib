pipeline {
  agent { docker { image 'python:3.10.6' } }
  stages {
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'flake8 calculator.py test_calculator.py --statistics'
        sh 'python test.py'
      }
    }
  }
}