pipeline {
    agent any
        environment {
            KOK     = "$WORKSPACE"
            SURUM   = "1.2.$BUILD_ID"
    }
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
         stage("Docker-build") {
             steps {
                  dir ("${DIZIN}") {
                       sh " docker build -t app.jar:latest . "
                       sh " docker run app-jar:latest "
                     }
              }
         }
    }
}