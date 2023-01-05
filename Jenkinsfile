pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        // install python dependencies
        bat 'pip install -r requirements.txt'
      }
    }
    stage('Test') {
      steps {
        // Flask unit test
        bat 'python -m unittest'
      }
    }
}
}
