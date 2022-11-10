pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'echo building' 
            }
        }
        stage('Test'){
            steps {
                sh 'echo testing'
                junit 'reports/**/*.xml' 
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo  deploying'
            }
        }
    }
}