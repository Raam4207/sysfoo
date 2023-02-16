pipeline{
    agent { label 'slave-2' }
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
            post{
                 always {
                      echo "This block always runs."
                 }
                }
        }
    }
}

