import groovy.json.JsonSlurper

@NonCPS
def param(){
    def p = new File("${WORKSPACE}/properties").withReader { r ->
        new JsonSlurper().parse( r )
    }
    
    
    println "All properties: " + p
    println "SonarProjectKey = " + p.sonarProperties.projectKey
    println "applicationName = " + p.applicationName
    println "tillerNamespace = " + p.tillerNamespace

}

def param2(){
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
      param()
      param2()
    }      
}
