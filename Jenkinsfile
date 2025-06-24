pipeline{
    agent {
        label 'AGENT-01'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    stages{
        stage('build'){
            steps{
                sh"""
                ls -ltr 
                npm install 
                """
                  }
        }  

    }
    post {
        always{
            echo 'i will reun always '
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