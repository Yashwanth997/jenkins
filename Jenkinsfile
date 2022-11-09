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
           input{
                message 'Send to deploy?'
                ok "Yes"
                echo 'testing the application'
           }
         }
       } 
       stage("deploy") {
      steps{
           input {
                message 'Send to Release?' 
                ok "YES"
                echo 'Deploying the application'
           }
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
