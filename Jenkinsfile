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
        echo 'testing the application..'
         }
       } 
       stage("deploy") {
      steps{
        input 'Send to Release?'
           lock("test"){
           echo 'locked test stage..'
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
