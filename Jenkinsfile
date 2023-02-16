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
             sh "curl -v -u admin:123 -T /var/lib/jenkins/workspace/dep/target/*.war 'http://3.110.48.199:8080//manager/text/deploy?path=/pipeline_maven'"
          }
        } 
        }
    }

