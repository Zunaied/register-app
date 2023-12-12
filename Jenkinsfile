pipeline {
    agent { label "jenkin-agent" }
    tools {
        jdk 'java17'
        maven 'maven3'
    }
    stages {
        stage("Clean Workspace") {
            steps {
                cleanWs()
            }
        }

        stage("Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Zunaied/register-app.git'
            }
        }

        stage("Build Application") {
            steps {
                script {
                    sh "mvn clean package"
                }
            }
        }

        stage("Test Application") {
            steps {
                script {
                    sh "mvn test"
                }
            }
        }
    }
}
