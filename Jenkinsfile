pipeline{
  agent any
  
  stages{
    stage('Build') {
      steps{
        echo "git fetching"
        git branch: 'main', url: 'https://github.com/thesilentcoderr/testHTML/'
        echo "fetch done"
      }
    }
    stage('Test') {
      steps{
        echo "Tranfering files to test"
        
      }
    }
  }
}
