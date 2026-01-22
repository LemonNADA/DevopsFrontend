pipeline {
    agent any
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
    }
}