pipeline {
    agent {
        docker {
            image 'maven:3.5.4-jdk-11'
	        args '-v /data/repos/.m2:/root/.m2'
         }
    }
    tools {
        maven 'maven'
        jdk 'Java11'
    }
    stages {
        stage('prepare') {
            steps {
               echo "prepare"
            }
        }
        stage('build') {
            steps {
               sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
               sh 'mvn test'
            }
        }
         stage('package') {
            steps {
               sh 'mvn package'
            }
        }
        stage('execute') {
            steps {
               sh '''
                 cd target
                 java -cp maven-hello-1.0.0-SNAPSHOT.jar fr.epsi.demo.Helloworld
               '''
            }
        }
    }
     post {
        always {
            sh 'ls target/'
            junit '**/surefire-reports/*.xml'
        }
    }
}
