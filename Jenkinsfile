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
