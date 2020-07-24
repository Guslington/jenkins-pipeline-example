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
        stage('deploy') {
            steps {
                echo 'deloying app'
            }
        }
    }
}