pipeline {
    agent any
    stages{
        stage("Checkout the code"){
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/rohanshinde2004/Free-style-demo.git'
            }
        }
        stage("Compile"){
            steps{
                sh 'mvn -B compile'
            }
        }
        stage("Test"){
            steps{
                sh 'mvn -B test'
            }
            post {
            always{
                junit keepProperties: true, stdioRetention: 'ALL', testResults: '**/target/surefire-reports/*.xml'
            }
            }
        }
        stage("package"){
            steps {
                sh 'mvn -B -ntp package -DskipTests'
            }
        }
    }
    post{
        success { echo 'Build success' }
        failure { echo 'Build failed' }
        }
}