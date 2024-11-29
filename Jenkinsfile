pipeline {
    agent any
    tools { maven 'M3' }
    
    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/soumyabrata09/SpringPetClinic.git'
            }
        }
        
        stage('build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        
        stage('test') {
            
            steps {
                
                sh 'mvn clean -e test'
            }
        }
        
        stage('package') {
            steps {
                sh 'mvn package'
            }
        }
        
        stage('deploy') {
            steps {
                sh 'java -jar /home/coder/.jenkins/workspace/PetClinicDSLPipeline/target/*.jar'
                // sh 'mvn deploy'
            }
        }
    }
}
