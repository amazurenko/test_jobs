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
        def scmUrl = scm.getUserRemoteConfigs()[0].getUrl()
        gitPRChecker('jenkins-coreci-secrettoken', scmUrl.split('/')[3], scmUrl, getLastCommit(-1))           
        param2()
    }      
}
