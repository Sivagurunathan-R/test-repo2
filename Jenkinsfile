pipeline {
    agent any
    
    tools {
        maven 'MAVEN_HOME' 
        
        jdk 'Java8'
    }
    stages {
  
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'MAVEN_HOME') {
                    bat 'mvn test'
                }
            }
        }
        
    }
}
