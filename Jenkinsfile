pipeline {
    agent any

    environment {
        PROJECT_PATH = '/var/www/teacher_project_name'
        PROJECT_USER = 'cheptsov'
        PROJECT_HOST = 'mshptop.ru'
    }
    
    stages {
        stage("install dependencies") {
            steps {
                sh "npm install"
            }
        }
        stage("start project") {
            steps {
                sh "npm run build_prod"
            }
        }
        stage("deploy") {
            steps {
                sh """
                    scp -r dist/* ${PROJECT_USER}@${PROJECT_HOST}:${PROJECT_PATH}/
                """
            }
        }
    }
}