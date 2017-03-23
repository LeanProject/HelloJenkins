// Jenkins file template. Purpose of this file is building a template for all Jenkins
// pipelines. 
node {

    // Prerequisits
    checkout scm

    // Automatic build stage 
    stage('\u2705 Build automation') {

    }

    // Run unittest 
    stage ('\u274C Unit test') {
     
    }

    // Static analysis
    stage ('\u274C Static analysis') {

    }
    
    //Deploy to DEV
    stage ('\u274C DEV deploy'){
    
    }
    
    //Basic DEV acceptance test
    stage ('\u274C Basic DEV acceptance test'){
    
    }
    
    //Perform load test
    stage ('\u274C Load test'){
    
    }
    
    //Perform acceptance test
    stage ('\u274C Acceptance test') {
    
    }
    
    //Deploy to STAGE
    stage ('\u274C STAGE deploy'){
    
    }
    
    // Send mail to inform about status on this build
    currentBuild.result = "SUCCESS"
    
    // Email on any failures, and on first success.
    try {
        currentBuild.result = "SUCCESS" 
    } finally {    
         if (currentBuild.result != 'SUCCESS' || currentBuild.getPreviousBuild().result != currentBuild.result) {
             emailext(subject: '${DEFAULT_SUBJECT}',
                     to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                                             [$class: 'RequesterRecipientProvider']]),
                     replyTo: '$DEFAULT_REPLYTO',
                     attachLog: true,
                     mimeType: 'text/html',
                     body: '${DEFAULT_CONTENT}')                
            }
    }

} //End of Jenkinsfile



    
