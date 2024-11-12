pipeline {
    agent any
    stages {
        stage("Git-Pull") {
                steps {
                        git branch: "master",
                        url: "https://github.com/ibrahimoztekin/simple-java-maven-app.git"
                }
            }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}