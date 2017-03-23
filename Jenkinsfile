// Jenkins file template. Purpose of this file is building a template for all Jenkins
// pipelines. 
node {

    // Source code checkout
    stage ('Source code checkout') {
      checkout scm
    }
    
    // Static analysis
    stage ('Static analysis \u274c') {

    }

    // Automatic build stage 
    stage('Build automation \u274c') {

    }
    
    // Run component test 
    stage ('Component test \u274c') {
     
    }
    
    // Analyse code quality 
    stage ('Analyse code quality \u274c') {
     
    }
    
    //Deploy to DEV
    stage ('DEV deploy \u274c'){
    
    }
    
    //Perform acceptance test
    stage ('Acceptance test \u274c') {
    
    }
    
    //Perform load test
    stage ('Load test \u274c'){
    
    }
    
    //Deploy to STAGE
    stage ('STAGE deploy \u274c'){
    
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



    
