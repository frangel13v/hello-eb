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
                        sh 'eb init'
			input 'input'
			sh '2'
                        sh 'docker-compose pull'
                        sh 'docker-compose up -d'
                        sh 'eb create'
                    }                    
                }
                
            }
        }
        

    }
}
