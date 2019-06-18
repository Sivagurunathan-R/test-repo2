pipeline {
  agent any
  
  tools{
  
    maven 'MAVEN_HOME'
    jdk 'Java8'
  }
  
  stages {
    
    stage('Maven Install') {
            steps {
                script {
                    /**
                     * Override maven in this stage
                     * you can also use 'tools {maven: "$mavenLocation"}'
                     *
                     * globalMavenSettingsConfig: Select a global maven settings element from File Config Provider
                     * jdk: Select a JDK installation
                     * maven: Select a Maven installation
                     */
                    withMaven(globalMavenSettingsConfig: "$mavenConfig", jdk: "$JDKVersion", maven: "$mavenLocation") {
                        /**
                         * To proceed to the next stage even if the current stage failed,
                         * enclose this stage in a try-catch block
                         */
                        try {
                            sh "mvn clean install"
                        } catch (Exception err) {
                            echo 'Maven clean install failed'
                            currentBuild.result = 'FAILURE'
                        } finally {
                            publishHTMLReports('Reports')
                        }
                    }
                }
    
  }
}
