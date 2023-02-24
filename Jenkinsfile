pipeline {
    agent any
    stages {
        stage('Git clone') {
            steps {
                git 'https://github.com/MY-AZ-400/hello-world.git'
            }
        }
        stage('Building war file') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Deploy to container') {
            steps {
                deploy adapters: [tomcat8(credentialsId: 'tomcat deployer', path: '', url: 'http://18.221.238.31:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
