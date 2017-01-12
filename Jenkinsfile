node {
stage ('Send mail') { 
    echo "send mail"
    currentBuild.result = "SUCCESS"
} //stage   
    
// Email on any failures, and on first success.
        try {
            //currentBuild.result = "FAILURE"
            //error "Fejl" 
        } finally { 
         echo currentBuild.result    
         if (currentBuild.result == 'SUCCESS' || currentBuild.getPreviousBuild().result != currentBuild.result) {
             // Settings should not be changed in this call. Change settings in email in Jenkins>Manage Jenkins>Configuration
             emailext(subject: '${DEFAULT_SUBJECT}',
                     //to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                     //                         [$class: 'RequesterRecipientProvider']]),
                     to: '$DEFAULT_RECIPIENTS',
                     replyTo: '$DEFAULT_REPLYTO',
                     attachLog: true,
                     //compressLog: true,
                     mimeType: 'text/html',
                     body: '${DEFAULT_CONTENT}') 
                     
                      
        }
        }
}