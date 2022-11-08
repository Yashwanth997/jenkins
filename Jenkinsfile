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
           options{
                lock ("test")
           }
        echo 'testing the application..'
         }
       } 
       stage("deploy") {
      steps{
        input 'Send to Release?'
        echo 'testing the application..'
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
