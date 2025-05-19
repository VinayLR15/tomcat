pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
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

        stage('Deploy WAR Locally') {
            steps {
                sh '''
                    # Local copy to Tomcat webapps directory
                    sudo cp target/MymavenWebApp01.war /opt/tomcat/webapps/
                '''
            }
        }
    }
}
