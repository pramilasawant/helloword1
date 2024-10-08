@Library('Jenkins_Pipeline_Library') _

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the repository
                checkout([$class: 'GitSCM', 
                branches: [[name: '*/main']],  // Specify the branch you want to checkout
                userRemoteConfigs: [[url: 'https://github.com/pramilasawant/helloword1.git']] // Update with your repository URL
                ])
            }
        }

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
