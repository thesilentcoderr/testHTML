pipeline{
  agent any
  
  stages{
    stage('GIT Clone') {
      echo "git fetching"
      git branch: 'main', url: 'https://github.com/thesilentcoderr/testHTML/'
      echo "fetch done"
    }
  }
}
