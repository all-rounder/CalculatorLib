pipeline {
  agent { docker { image 'python:3.10.6' } }
  stages {
    stage('build') {
      steps {
        sh '''
        python3 -m venv venv
        . .venv/bin/activate
        pip install -r requirements.txt
        '''
      }
    }
    stage('test') {
      steps {
        sh '''
        . .venv/bin/activate
        flake8 --exclude=venv* --statistics
        pytest -v --cov=calculator
        '''
      }
    }
  }
}