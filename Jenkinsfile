pipeline{
    agent {
        label 'AGENT-01'
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    environment{
        def appversion =''
    }

    stages{
        stage('read_version'){
            steps{
               script{
                def packagejson = readJSON file: 'package.json'
                 appversion = packagejson.version
                echo "appversion is  $appversion"

               }
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
        stage('build'){
            steps{
                sh"""
                zip -r backend-$appversion.zip - x Jenkinsfile - x backend-$appversion.zip 
                ls -ltr 
                """
            }
        }
    
}
    post {
        always{
            echo 'i will run always '
           // deleteDir()
        }
        success {
            echo 'pipeline is successfully exuited '
        }
        failure {
            echo 'pipeline is excuiation failed '
        }
    }
}