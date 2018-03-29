pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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