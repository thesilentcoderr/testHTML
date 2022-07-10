pipeline{
  agent any
  
  stages{
    stage('Git Fetch') {
      steps{
        echo "git fetching"
        git branch: 'main', url: 'https://github.com/thesilentcoderr/testHTML/'
        echo "fetch done"
      }
    }
    stage('Build') {
      steps{
        echo "Tranfering files to test"
        sh 'sudo cp -f * /var/www/html'
        echo "Data Tranferred"
        echo 'Website deployed on 13.235.8.158'
      }
    }
    stage('Test') {
        steps{
            echo "Test Success"
        }
        input{
            message "Do you want to approve for prod ?"
        }
    }
    stage('Deploy') {
        steps{
            sshPublisher failOnError: true, publishers: [sshPublisherDesc(configName: 'webserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'sudo mv /home/ec2-user/* /var/www/html/', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/ec2-user', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: true)]
            echo 'website deployed to prod'
        }
    }
}
  }
