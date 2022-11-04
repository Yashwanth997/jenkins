pipeline {
  
    agent any
  stages{
   when {
  branch '**/test-*'
  beforeOptions true
  beforeInput true
  beforeAgent true
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
}
