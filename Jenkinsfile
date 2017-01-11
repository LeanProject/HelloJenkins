node {
    stage ('Send mail') {
        echo "Send mail stage started"
        try {
            sh 'exit 1'
        } finally {
            echo "Sending mail"
            mail bcc: '', body: 'Sending a mail til TLA', cc: '', from: 'platform@tv2.dk', replyTo: '', subject: 'Sending mail', to: 'tla@tv2.dk'
            step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'tla@tv2.dk', sendToIndividuals: true])
        }

    }        
}
