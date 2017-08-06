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

node{
    stage("Preparation"){
      checkout scm
    }
    stage("Load properties"){
      param()
    }      
}
