/*
* Jenkins Config comes here
*/
stages[
  stage('CLone') {
    steps{
      git branch: 'master'
      url: 'https://github.com/trilioit/todoApp.git'
    }
  }
  stage('Build') {
    steps {
      sh '''
      docker build -t todoApp:${BUILD_NUMBER}
      '''
    }
  }
  stage('Test') {
    steps {
      sh '''
      docker run -it todoApp:${BUILD_NUMBER}
      '''
    }
  }
  stage('Package') {
    steps {
      sh '''
      docker push trilionweb/apps/todoApp:${BUILD_NUMBER}
      '''
    }
  }
  stage('Deploy') {
    steps {
      sh '''
      echo "DevOps to do: Add some 1337 deploy logic here"
      '''
    }
  }
]