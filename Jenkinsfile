pipeline {
  agent any

  /*
   * If the env path is not configured in Jenkins define it
   * within the environment structure
   *
    environment {
      PATH = "/usr/local/bin:/usr/bin:/bin:${env.PATH}"
    }
  */


  stages {
    stage('build-api-test-image') {
      steps {
        script {
          buildDockerImage()
        }
      }
    }
  }
}

def buildDockerImage() {
  echo "Building of node application is starting..."
  sh "docker build -t mmatovski/api-tests ."

  echo "Pushing image to docker registry..."
  sh "docker push mmatovski/api-tests"
}

