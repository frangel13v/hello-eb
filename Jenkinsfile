pipeline {
    agent any

    options {
        timestamps()
        ansiColor('xterm')
    }

    stages {
        stage('Deploy') {
            steps {
                withAWS(credentials: 'angelfr-aws-credentials') {
                   sshagent(['ssh-amazon']) {
                        sh 'eb create mi-entorno-dev'
                    }                    
                }
                
            }
        }
        

    }
}
