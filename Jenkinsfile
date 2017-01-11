node {
    stage ('Send mail') { 
        def Subject = "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) is finished"
        // Email on any failures, and on first success.
            emailext(body: '${DEFAULT_CONTENT}', 
                     attachLog: true,
                     mimeType: 'text/html',
                     replyTo: '$DEFAULT_REPLYTO', 
                     subject: Subject,
                     //'${DEFAULT_SUBJECT}',
                     from: "jenkins@tv2.dk",
                     to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                                             [$class: 'RequesterRecipientProvider']])) 
        /*mail (to: to,
         subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) is waiting for input",
         body: "Please go to ${env.BUILD_URL}.");*/
      } //stage   
} //node
