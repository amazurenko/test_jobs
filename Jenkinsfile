import groovy.json.JsonSlurper

@NonCPS
def param(){
    def inputFile = new File("${WORKSPACE}/properties")
   // InputJSON = new JsonSlurper().parseText(inputFile.text)
    //InputJSON.each{ println it }
        def game = inputFile.withReader { r ->
        new JsonSlurper().parse( r )
    }
    println game
}

node{
    stage("Preparation"){
      checkout scm
    }
    stage("Load properties"){
      param()
    }      
}
