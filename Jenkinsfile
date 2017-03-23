// Jenkins file template. Purpose of this file is building a template for all Jenkins
// pipelines. 
node {

    // Source code checkout
    stage ('Source code checkout \u2600') {
      checkout scm
    }
    
    // Static analysis
    stage ('Static analysis \u2601') {

    }

    // Automatic build stage 
    stage('Build automation \u2601') {

    }

    
    // Run component test 
    stage ('Component test \u2601') {
     
    }
    
    // Analyse code quality 
    stage ('Analyse code quality \u2601') {
     
    }
    
    //Deploy to DEV
    stage ('DEV deploy \u2601'){
    
    }
    
    //Perform acceptance test
    stage ('Acceptance test \u2601') {
    
    }
    
    //Perform load test
    stage ('Load test \u2601'){
    
    }
    
    //Deploy to STAGE
    stage ('STAGE deploy \u2601'){
    
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



    
