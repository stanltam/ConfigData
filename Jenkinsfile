pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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
    }
}