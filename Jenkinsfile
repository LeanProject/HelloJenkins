node {
    stage ('Send mail') {    
        // Email on any failures, and on first success.
            echo currentResult
            if (currentResult = 'SUCCESS' { 
            emailext(body: '${DEFAULT_CONTENT}', 
                     attachLog: true,
                     mimeType: 'text/html',
                     replyTo: '$DEFAULT_REPLYTO', 
                     subject: '${DEFAULT_SUBJECT}',
                     from: "jenkins@tv2.dk",
                     to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                                             [$class: 'RequesterRecipientProvider']])) 
                
            }
        /*mail (to: to,
         subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) is waiting for input",
         body: "Please go to ${env.BUILD_URL}.");*/
      } //stage   
} //node
