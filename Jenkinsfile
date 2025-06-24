pipeline{
    agent {
        label 'AGENT-01'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }

    stages{
        stage('install dependencies '){
            steps{
                sh"""
               
                npm install 
                ls -ltr 
                """
                  }
        }  

    }
    post {
        always{
            echo 'i will run always '
            deleteDir()
        }
        success {
            echo 'pipeline is successfully exuited '
        }
        failure {
            echo 'pipeline is excuiation failed '
        }
    }
}