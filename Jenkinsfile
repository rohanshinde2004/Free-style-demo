pipeline {
    agent any 
    stages{
        stage('checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/rohanshinde2004/Free-style-demo.git'
            }
        }
        stage('Versions'){
            steps{
                sh 'mvn --version'
                sh 'java -version'
            }
        }
        stage('compile'){
            steps{
                sh 'mvn -B compile'
                //Compile the source code of the project.
            }
        }
        stage('test'){
            steps{
                sh 'mvn -B test'
                //Run tests using a suitable unit tests
            }
        }
        stage('package'){
            steps{
                sh 'mvn -B -ntp package -DskipTests'
                //package the compiled code in its distributable format, such as a JAR.
            }
        }
    }
}