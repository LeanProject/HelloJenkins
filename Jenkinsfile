node {
stage ('Send mail') { 
    echo "send mail"
    currentBuild.result = "SUCCESS"
} //stage   
echo currentBuild.result    
echo currentBuild.displayName
    
// Email on any failures, and on first success.
        try {
            //currentBuild.result = "FAILURE"
            //error "Fejl" 
        } finally { 
         echo currentBuild.result    
         if (currentBuild.result != 'SUCCESS' || currentBuild.getPreviousBuild().result != currentBuild.result) {
            emailext(body: '${DEFAULT_CONTENT}', 
                     attachLog: true,
                     compressLog: true,
                     mimeType: 'text/html',
                     replyTo: '$DEFAULT_REPLYTO', 
                     subject: '${DEFAULT_SUBJECT}',
                     to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                                             [$class: 'RequesterRecipientProvider']])) 
        }
        }
}