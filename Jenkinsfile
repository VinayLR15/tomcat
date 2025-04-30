pipeline {
    agent any

    tools {
        maven 'Maven'     // <-- Must match exactly what's configured in Jenkins
        jdk 'JDK'         // <-- Ditto
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/VinayLR15/tomcat.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy WAR') {
            steps {
                // Replace these values with real ones
                sh 'scp target/MymavenWebApp01.war vinay@192.168.1.50:/opt/tomcat/webapps/'
            }
        }
    }
}

