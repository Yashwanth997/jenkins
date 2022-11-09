pipeline {
     agent any
     stages{
     stage("build") {
            input {
              message "Send to Test?"
                 ok "Yes"
            steps{
       echo 'building the application..'
            }
         }
       }
        stage("test") {
           input{
                message "Send to deploy?"
                ok "Yes"
            steps{
                echo 'testing the application'
           }
         }
       } 
       stage("deploy") {
           input {
                message 'Send to Release?' 
                ok "YES"
            steps{
                echo 'Deploying the application'
           }
         }
       }
      stage("release") {
           steps {
        echo 'releasing the application..'
      }
    }
  }
}
