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
        stage('read_version'){
            steps{
               
                def packagejson = readJSON file: 'package.json'
                def appversion = packagejson.appversion
                echo "appversion is  $appversion"

               
            }
        }
        stage('install dependencies '){
            steps{
                sh"""
               
                npm install 
                ls -ltr 
                echo $appversion
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