pipeline {
  
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
