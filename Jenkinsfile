pipeline {
  
    agent any
     stages{
     stage("build") {
        steps{
        input 'Send to Test?'
         echo 'building the application..'
      }
    }
       stage("test") {
      steps{
        input 'Send to Deploy?'
        echo 'testing the application..'
        if (!continueBuild) {
    currentBuild.result = 'ABORTED'
    error('Stopping early…')
        }
      }
    }
    stage("deploy") {
        steps{
        input 'Send to Release?'
        echo 'deploying the application..'
      }
    }
      stage("release") {
      steps{
        input 'approve release?'
        echo 'releasing the application..'
      }
    }
  }
}
