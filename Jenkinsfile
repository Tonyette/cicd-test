pipeline {
    agent any
    stages {
        stage('building node') {
            steps {
                echo 'building'
                nodejs('node'){
                    sh 'npm install'
                    sh 'node index.js'
                    }
                }
            }
        stage('testing node') {
            steps {
                echo 'testing'
                nodejs('node')
                sh './script/test.js'
            }       
        }
    }
}
