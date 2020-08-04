pipeline {
    environment {
        TEST = 'test'
    }

    agent any

    stages {
        stage('build') {
            steps {
                echo "GIT_COMMIT: ${env.GIT_COMMIT}"
                echo "GIT_BRANCH: ${env.GIT_BRANCH}"
                echo "GIT_URL: ${env.GIT_URL}"
            }
        }
        stage('test') {
            steps {
                echo 'testing app'
            }
        }
        stage('deploy dev') {
            when {
                anyOf {
                    branch 'develop'; branch 'feature/*'
                }
            }
            steps {
                echo 'deloying app to dev'
            }
        }
        stage('deploy test') {
            when {
                branch 'develop'
            }
            steps {
                echo 'deloying app to test'
            }
        }
        stage('deploy uat') {
            when {
                branch 'master'
            }
            steps {
                echo 'deloying app to uat'
            }
        }
        stage('deploy prod') {
            when {
                branch 'master'
            }
            input {
                message 'promote app to production?'
            }
            steps {
                echo 'deloying app to pr'
            }
        }
    }
}