pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t minecraft . '
      }
    }

    stage('Deploy') {
      steps {
        sh 'docker rm -f minecraft'
        sh 'docker run -d -e EULA=true -p 25565:25565 -v ${PWD}/minecraftServer:/data --name minecraft minecraft '
      }
    }

  }
}