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
      	input(message: "Approve/Abort '${ENVIRONMENT}' deployment. If aborted kindly mention the reason in next step.", ok: 'Approve')//, submitter: env.SIGN_OFF_SUBMITTERS_QA)
	}
	catch(parentErr) {
	try {
        input(message: 'Revert the build to older stable version?', ok: 'Approve')//, submitter: env.SIGN_OFF_SUBMITTERS_QA)

        // Get back the scaled down version up
        JenkinsUtilities.FromConfigScaleUpPreviousECSService(AWS_ROLE)
	// Revert Blue Green change for QA server
									JenkinsUtilities.FromConfigSwitchTargetGroupWeigthsCloudformation(AWS_ROLE)
								}
								catch(err) {
									// Ignore this abort.
								}

								// Build abort reason
								def userAbort = input(id: 'userAbort',
													message: BuildAbortMessage,
													//  submitter: env.SIGN_OFF_SUBMITTERS_QA,
													parameters: [
														[$class: 'TextParameterDefinition', defaultValue: 'Add reason for build abort', description: '', name: 'Remarks']
													])
								def user = parentErr.getCauses()[0].getUser()
								String remarksUserName = "Aborted by: [${user}]"
								echo (userAbort)
								currentBuild.result = 'ABORTED'
								RemarksUserName = "${remarksUserName}<br/><b>${userAbort}</b>"

								throw parentErr
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
