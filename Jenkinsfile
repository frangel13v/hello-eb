pipeline {
    agent any

    options {
        timestamps()
        ansiColor('xterm')
    }

    stages {
        stage('Deploy') {
            steps {
                withAWS(credentials: 'angelfr-aws-credentials', region: 'eu-west-1') {
                   dir("proyecto") {
                        sh 'eb create mi-entorno-dev'
                    }
                }
                
            }
        }
        

    }
}
