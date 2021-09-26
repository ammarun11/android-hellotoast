pipeline {
    agent any
    
    triggers {
        pollSCM('*/1 * * * *')
    }

    stages {
        stage('Pull') {
            steps {
                git 'https://github.com/ammarun11/android-hellotoast.git'
            }
        }

        stage('Build') {
            steps {
                sh "gradle clean build"
            }
            post {
                failure {
                    mail to: 'cintadamai46@gmail.com', subject: 'Build failed', body: 'Please fix!'
                }
            }
        }
    }
}
