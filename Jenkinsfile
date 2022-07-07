pipeline{
  agent any
  
  stages{
    stage('GIT Clone') {
      steps{
        echo "git fetching"
        git branch: 'main', url: 'https://github.com/thesilentcoderr/testHTML/'
        echo "fetch done"
      }
    }
  }
}
