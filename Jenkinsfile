// Jenkins file template. Purpose of this file is building a template for all Jenkins
// pipelines. 
node {

    // Prerequisits
    checkout scm

    // Automatic build stage 
    stage('Build automation') {

    }

    // Run unittest 
    stage ('Unit test') {
     
    }

    // Static analysis
    stage ('Static analysis') {

    }
    
    //Deploy to DEV
    stage ('DEV deploy')
    {
    
    }
    
    //Perform load test
    stage ('Load test')
    {
    
    }
    
    //Perform acceptance test
    {
    
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



    
