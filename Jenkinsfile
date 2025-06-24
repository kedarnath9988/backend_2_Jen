pipeline{
    agent {
        label 'AGENT-01'
    }
    options {
        timeout(time: 30, units: 'MINUTES')
        diableconcurrentBuilds()
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
        failed {
            echo 'pipeline files please check once '
        }
    }
}