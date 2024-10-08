@Library('Jenkins_pipeline_Library') _

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                buildHelloApp(appName: 'helloworldapplication', version: '1.0.0')
            }
        }

        stage('Test') {
            steps {
                testHelloApp(appName: 'helloworldapplication')
            }
        }

        stage('Deploy') {
            steps {
                deployHelloApp(appName: 'helloworldapplication', env: 'prod', namespace: 'production', version: '1.0.0')
            }
        }
    }
}
