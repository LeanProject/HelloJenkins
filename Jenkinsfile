def to = emailextrecipients([[$class: 'CulpritsRecipientProvider'],
                             [$class: 'DevelopersRecipientProvider'],
                             [$class: 'RequesterRecipientProvider']])

node {
     echo to
     input 'Ready to send mail?';
     stage ('Send mail') {
        mail (to: to,
         subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) is waiting for input",
         body: "Please go to ${env.BUILD_URL}.");
      } //stage   
} //node
