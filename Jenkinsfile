pipeline {

    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'master',
                url: 'https://github.com/Hasan-Nazeem/ecommerce-app.git'
            }
        }


        stage('Deploy Application') {
            steps {
                sh '''
                docker compose down
				docker compose up -d --build --force-recreate
				docker image prune -f
                '''
            }
        }
    }
}
