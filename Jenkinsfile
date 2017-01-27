node {


stage('SonarQube analysis') {
    // requires SonarQube Scanner 2.8+
    
    //def scannerHome = tool 'SonarQube Scanner 2.8';
      
    //withSonarQubeEnv('SonarQube') {
        sh "${scannerHome}/bin/sonar-   scanner"
    }
}
stage ('HTML publish') {
    publishHTML([allowMissing: false, 
                 alwaysLinkToLastBuild: false, 
                 keepAll: false, 
                 reportDir: '', 
                 reportFiles: 'index.html', 
                 reportName: 'HTML Report'])
}


stage ('Send mail') { 
    echo "send new mail"
    currentBuild.result = "SUCCESS"
} //stage   
    
// Email on any failures, and on first success.
        try {
            currentBuild.result = "SUCCESS"
            //error "OK" 
        } finally { 
         echo currentBuild.result    
         if (currentBuild.result != 'SUCCESS' || currentBuild.getPreviousBuild().result != currentBuild.result) {
             // Settings should not be changed in this call. Change settings in email in Jenkins>Manage Jenkins>Configuration
             emailext(subject: '${DEFAULT_SUBJECT}',
                     to: emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                                             [$class: 'RequesterRecipientProvider']]),
                     replyTo: '$DEFAULT_REPLYTO',
                     attachLog: true,
                     mimeType: 'text/html',
                     body: '${DEFAULT_CONTENT}')                
        }
        }
}



    
