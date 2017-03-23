// Jenkins file template. Purpose of this file is building a template for all Jenkins
// pipelines. 
node {

    // Source code checkout
    stage ('Source checkout \u2618') {
      checkout scm
    }
    
    // Static analysis
    stage ('Static analysis') {

    }

    // Automatic build stage 
    stage('Build automation \u2618') {

    }

    // Run unittest 
    stage ('Unit test \u2601 ') {
     
    }

    node {
    // This is the current syntax for invoking a build wrapper, naming the class.
    wrap([$class: 'AnsiColorBuildWrapper']) {
        // Just some echoes to show the ANSI color.
        stage "\u001B[31mI'm Red\u001B[0m Now not"
        }
    }
    
    //Deploy to DEV
    stage ('DEV deploy'){
    
    }
    
    //Basic DEV acceptance test
    stage ('Basic DEV acceptance test'){
    
    }
    
    //Perform load test
    stage ('Load test'){
    
    }
    
    //Perform acceptance test
    stage ('Acceptance test') {
    
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



    
