import groovy.json.JsonSlurper

@NonCPS
def param(){
    def properties = new File("${WORKSPACE}/properties").withReader { r ->
        new JsonSlurper().parse( r )
    }
    
    
    println properties
    println properties.sonarProperties.projectKey
    
}

node{
    stage("Preparation"){
      checkout scm
    }
    stage("Load properties"){
      param()
    }      
}
