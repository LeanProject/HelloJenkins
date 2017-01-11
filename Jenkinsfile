node {
    stage ('Send mail') {
        sh 'java -verdion'
        echo "Send mail stage started"
        step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: emailextrecipients([[$class: 'CulpritsRecipientProvider'], [$class: 'RequesterRecipientProvider']])])
        /*try {
            //sh 'exit 1'
        } finally {
            echo "Sending mail"
            mail bcc: '', 
                body: 'Sending a mail til TLA',
                cc: '', 
                from: 'platform@tv2.dk', 
                replyTo: '', 
                subject: 'Sending mail', 
                to: 'tla@tv2.dk'
        }*/

    }        
}
