pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'checking out source..'
				checkout scm
				sh 'chmod 770 build.sh'
				sh './build.sh'
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