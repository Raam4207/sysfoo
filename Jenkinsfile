pipeline{
    agent any
    tools{
        maven 'Maven'
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
        stage ('Deploy') {
          steps {
            script {
              deploy adapters: [tomcat10(credentialsId: 'tomcat_credential', path: '', url: 'http://3.110.48.199:8080')], contextPath: '/pipeline', onFailure: false, war: 'target/*.war' 
            }
          }
        } 
        }
    }

