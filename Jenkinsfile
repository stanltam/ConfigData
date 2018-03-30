pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'checking out source..'
				checkout scm
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'stanltam@gmail.com', sendToIndividuals: true])

            }
        }
        stage('Notification') {
            steps {
                echo 'Sending Email....'
              mail bcc: '', body: 'Build Completed', cc: '', from: '', replyTo: '', subject: '[Jenkin Pipeline]Build Completed', to: 'stanltam@gmail.com'
            }
        }		
    }
}