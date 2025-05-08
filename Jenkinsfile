pipeline {
    agent any

    tools {
        maven 'Maven'     // Must match exactly with what is configured in Jenkins global tools
        jdk 'JDK'         // Same here
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
                // Using SCP with -o StrictHostKeyChecking=no to suppress interactive prompts
                sh '''
                    scp -o StrictHostKeyChecking=no target/MymavenWebApp01.war vinay-l-r@192.168.201.62:/opt/tomcat/webapps/
                '''
            }
        }
    }
}
