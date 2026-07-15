pipeline {
    agent any

   triggers{
      cron('* * * * *')
}

    stages {
        stage('Build') {
            steps {
                echo 'Compiling the C program...'
                sh 'gcc hello.c -o hello'
            }
        }

        stage('Test') {
            steps {
                echo 'Running the C program...'
                sh './hello'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
