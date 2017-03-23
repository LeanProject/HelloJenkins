// Jenkins file template. Purpose of this file is building a template for all Jenkins
// pipelines. 
node {

    // Source code checkout
    stage ('Source code checkout \u2601') {
      checkout scm
    }
    
    // Static analysis
    stage ('Static analysis') {

    }

    // Automatic build stage 
    stage('Build automation') {

    }

    
    // Run component test 
    stage ('Component test') {
     
    }
    
    // Analyse code quality 
    stage ('Analyse code quality') {
     
    }
    
    //Deploy to DEV
    stage ('DEV deploy'){
    
    }
    
    //Perform acceptance test
    stage ('Acceptance test') {
    
    }
    
    //Perform load test
    stage ('Load test'){
    
    }
    
    //Deploy to STAGE
    stage ('STAGE deploy'){
    
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



    
