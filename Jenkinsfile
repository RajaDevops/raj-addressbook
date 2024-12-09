pipeline {
   agent none
   tools{
//     jdk "myjava"
        maven "Maven 3.9.9"
   }
    stages {
        stage('Compile') { //prod
        agent any
            steps {
                echo "Compile the code"
                sh "mvn compile"
            }
        }
         stage('UnitTest') { //test
         agent any
            steps {
                echo "Test the code"
                sh "mvn test"
            }
        }
         stage('Package') {//dev
        agent {label 'slave-node'}
            steps {
                echo "Package the code"
                sh "mvn package"
            }
        }
    }
}
