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
                echo 'this is build stage 
                """
                  }
             }
        stage('test'){
            steps{
                sh"""
                    echo 'this is test'
                """
            }
        }  
        stage('deploy'){
            steps{
                sh"""
                echo 'this is deploy stage'
                """
            }
        }  

    }
    post {
        always{
            echo 'i will reun always '
        }
        success {
            echo 'pipeline is successfully exuited '
        }
        failure {
            echo 'pipeline is excuiation failed '
        }
    }
}