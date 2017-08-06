def param(){
    def p = load("${WORKSPACE}/gproerties")
    
    println "All properties2: " + p
    println "SonarProjectKey2 = " + p.sonarProperties.projectKey
    println "applicationName2 = " + p.applicationName
    println "tillerNamespace2 = " + p.tillerNamespace

}


node{
    stage("Preparation"){
      checkout scm
    }
    stage("Load properties"){
      getBuildParameters()
         withCredentials([string(credentialsId: 'jenkins-coreci-secrettoken', variable: 'creds')]) {
            def scmUrl = scm.getUserRemoteConfigs()[0].getUrl().split('/')
            gitPRChecker("${creds}", scmUrl[3], scmUrl, getLastCommit(-1))    
        }       
        
      
      param2()
    }      
}
