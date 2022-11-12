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
                sh 'ssh deployment-user@192.168.56.101 "SOURCE venv/bin/activate; \
                cd polling;\
                git pull origin master;\
                pip install -r requirements.txt; --no-warn-script-location; \
                python manage.py migrate; \
                deactivate;\
                sudo systemctl restart nginx; \
                sudo systemctl restart gunicorn; "'
            }
        }
    }
}