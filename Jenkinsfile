pipeline {
    agent any

    tools {
        maven 'Maven_3.8.7'
        jdk 'JDK_17'
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
                // Replace these with actual credentials or use SSH agent credentials in Jenkins
                sh 'scp target/MymavenWebApp01.war user@your-server:/opt/tomcat/webapps/'
            }
        }
    }
}
