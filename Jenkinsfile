node {
stage ('Send mail') { 
    echo "send mail"
} //stage   
    
// Email on any failures, and on first success.
        try {
          error "Fejl"  
        } finally { 
         echo currentBuild.result    
         //if (currentBuild.result != 'SUCCESS' || currentBuild.getPreviousBuild().result != previousResult) {
            emailext(body: '${DEFAULT_CONTENT}', 
                     attachLog: true,
                     mimeType: 'text/html',
                     replyTo: '$DEFAULT_REPLYTO', 
                     subject: '${DEFAULT_SUBJECT}',
                     from: "jenkins@tv2.dk",
                     to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                                             [$class: 'RequesterRecipientProvider']])) 
        //}
        }
}