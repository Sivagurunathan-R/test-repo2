pipeline {
  agent any
  
  tools{
  
    maven 'MAVEN_HOME'
    jdk 'Java8'
  }
  
  stages {
    stage('initialize'){
      steps {
        
        sh '''
        echo "PATH = ${PATH}"
echo "M2_HOME = ${M2_HOME}"
        '''
      }
    }
    
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }
  }
}
