pipeline {
    agent any
    stages {
        stage('building node') {
            steps {
                echo 'building'
                nodejs('node'){
                    sh 'npm install'
                    }
                }
            }
        stage('testing node') {
            steps {
                echo 'testing'
                nodejs('node') {
                sh 'npm test'
            }       
        }
    }        
        stage('deploying app') {
            steps {
                echo 'deploying'
                sh 'ssh tonia@162.222.180.4'
                sh 'cd ~/cicd-test'
                sh 'git pull https://github.com/Tonyette/cicd-test.git'
                sh 'npm install --production'
                sh 'pm2 start index.js'
                sh 'exit'
            }
        }
    }
}
