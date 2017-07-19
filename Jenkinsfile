@Library('qameta') _

pipeline {
    agent { label 'java' }
    parameters {
        booleanParam(name: 'RELEASE', defaultValue: false, description: 'Perform release?')
        string(name: 'RELEASE_VERSION', defaultValue: '', description: 'Release version')
        string(name: 'NEXT_VERSION', defaultValue: '', description: 'Next version (without SNAPSHOT)')
    }
    stages {
        stage('Build') {
            steps {
                gradleBuild {
                    tasks = 'build'
                }
            }
        }
    }
    post {
        always {
            deleteDir()
        }
    }
}