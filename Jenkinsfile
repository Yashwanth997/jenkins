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
        input 'Send to deploy?'
         }
       } 
       stage("deploy") {
      steps{
        input 'Send to Release?' 
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
