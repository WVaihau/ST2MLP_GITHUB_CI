pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        // install python dependencies
        bat 'pip install -r requirements.txt'
      }
    }
}
