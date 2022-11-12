pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'pip3 install -r requirements.txt' 
            }
        }
        stage('Test'){
            steps {
                sh 'echo its pass the test stage'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo  deploying to production'
            }
        }
    }
}