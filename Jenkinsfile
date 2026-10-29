pipeline {
    agent any 
    stages {
        stage("Hello"){
            steps {
                echo "Hello from declarative pipeline"
                sh "whoami && hostname && date"
            }
        }
    }
}