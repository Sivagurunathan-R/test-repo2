pipeline {
  agent any
  
  tools{
  
    maven 'MAVEN_HOME'
    jdk 'Java8'
  }
  
  stages {
    
    
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }
  }
}
