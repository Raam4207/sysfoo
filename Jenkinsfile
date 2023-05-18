pipeline{
    agent any
    tools{
        maven 'maven 3.8.6'
    }
    stages{
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('test'){
            steps{
                sh 'mvn clean test'
            }
        }
        stage('package'){
            steps{
                sh 'mvn package -DskipTests'
            }
        }
        }
    }

