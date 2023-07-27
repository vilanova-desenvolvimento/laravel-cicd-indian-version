pipeline {
    agent any
    environment {
        APP_NAME="Laravel"
        APP_ENV="local"
        APP_KEY="base64:F4HMNv1tmq4ajIzJ4zRzvj/qHOD3iZAVK5JVD8fx7nM="
        APP_DEBUG=true
        APP_URL="http://localhost"

        LOG_CHANNEL="stack"
        LOG_LEVEL="debug"

        DB_CONNECTION="mysql"
        DB_HOST="database"
        DB_PORT=3306
        DB_DATABASE="default"
        DB_USERNAME="laravel"
        DB_PASSWORD="secret"

        BROADCAST_DRIVER="log"
        CACHE_DRIVER="file"
        FILESYSTEM_DISK="local"
        QUEUE_CONNECTION="sync"
        SESSION_DRIVER="file"
        SESSION_LIFETIME=120

        MEMCACHED_HOST="127.0.0.1"

        REDIS_HOST="redis"
        REDIS_PASSWORD="secret"
        REDIS_PORT=6379

        MAIL_MAILER="smtp"
        MAIL_HOST="mailpit"
        MAIL_PORT=1025
        MAIL_FROM_ADDRESS="hello@example.com"
        MAIL_FROM_NAME="${APP_NAME}"

        AWS_DEFAULT_REGION="us-east-1"
        AWS_USE_PATH_STYLE_ENDPOINT=false
      
        PUSHER_PORT=443
        PUSHER_SCHEME="https"
        PUSHER_APP_CLUSTER="mt1"

        VITE_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
        VITE_PUSHER_HOST="${PUSHER_HOST}"
        VITE_PUSHER_PORT="${PUSHER_PORT}"
        VITE_PUSHER_SCHEME="${PUSHER_SCHEME}"
        VITE_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"

    }
    stages {
        stage('Clone') {
            steps {              
                sh "git branch: 'main', credentialsId: 'github-jenkins-token', url: 'https://github.com/vilanova-desenvolvimento/laravel-cicd-indian-version'" 
            }
        }
        stage('Build') {
            steps {              
                sh 'docker compose up -d' 
            }
        }
    }
}
