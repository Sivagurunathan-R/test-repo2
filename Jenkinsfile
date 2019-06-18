pipeline {
  agent any
  
  tools{
  
    maven 'MAVEN_HOME'
    jdk 'Java8'
  }
  
  stages {
    
    stage('maven_install'){
      
      steps{
      script{
      
        withMaven(globalMavenSettingsConfig : "$mavenConfig", jdk : "$JDKVersion" , maven :"$mavenLocation" )
        
      }
      }
    }
    
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }
  }
}
