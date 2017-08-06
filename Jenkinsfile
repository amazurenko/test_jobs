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
        def scmUrl = scm.getUserRemoteConfigs()[0].getUrl().split('/')
        println "isPR = " + gitPRChecker('jenkins-coreci-secrettoken', scmUrl[3], scmUrl[4].replace('.git',''), getLastCommit(-1))           
        param()
    }      
}
