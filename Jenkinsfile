pipeline {
  
    agent any
  stages{
    stage("build"){
      steps{
        echo 'building the application..'
      }
    }
    stage("test"){
      steps{
        input 'Send to Deploy?'
        echo 'testing the application..'
      }
    }
    stage("deploy"){
      steps{
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
