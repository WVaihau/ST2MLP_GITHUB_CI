pipeline {
  // As I am on window, sh is replaced by bat
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
    stage('Deploy') {
      steps {
        // Build docker image
        bat 'docker build -t kh-flask-api .'
        // Run in a container
        bat 'docker run -d -p 5000:5000 kh-flask-api'
      }
    }
}
}
