pipeline {
  
    agent any
  stages{
    stage("build"){
      steps{
        input 'Send to Test?'
        echo 'building the application..'
      }
    }
    stage("test"){
      steps{
        input 'Send to Deploy?'
        def userAbort = input(id: 'userAbort',
				message: BuildAbortMessage
        echo 'testing the application..'
      }
    }
    stage("deploy"){
      steps{
        unstable 'unstable'
        input 'Send to Release?'
        echo 'deploying the application..'
      }
    }
      stage("release"){
      steps{
        echo 'releasing the application..'
      }
    }
  }
}
