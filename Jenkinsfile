def Culprit   = emailextrecipients([[$class: 'CulpritsRecipientProvider']])
def Developer = emailextrecipients([[$class: 'DevelopersRecipientProvider']])
def Requester = emailextrecipients([[$class: 'RequesterRecipientProvider']])

node {
     echo Culprit
     echo Developer
     echo Requester
     stage ('Send mail') {
        mail (to: "tla@sd.dk",
         subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) is waiting for input",
         body: "Please go to ${env.BUILD_URL}.");
      } //stage   
} //node
