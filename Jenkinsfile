pipeline {
 agent any

 stages {

  stage('Clone') {
   steps {
    git 'YOUR_GITHUB_REPO'
   }
  }

  stage('Build Docker') {
   steps {
    sh 'docker build -t devops-app .'
   }
  }

  stage('Run Container') {
   steps {
    sh '''
    docker rm -f app || true
    docker run -d --name app -p 3000:3000 devops-app
    '''
   }
  }
 }
}
