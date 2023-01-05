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
      // Note : We supposed that Docker CLI is connected and have access to the repo
      steps {
        // Build docker image
        bat 'docker build -t kh-flask-api .'
        // Associate tag to docker hub repo
        bat 'docker tag kh-flask-api wvaihau/jenkins-ci'
        // Deploy to docker hub
        bat 'docker push wvaihau/jenkins-ci:latest'
      }
    }
}
}
