import groovy.json.JsonSlurper

@NoCPS
def param(){
    def inputFile = new File("properties")
    InputJSON = new JsonSlurper().parseText(inputFile.text)
    InputJSON.each{ println it }
}

node{
    stage("Preparation"){
      checkout scm
    }
    stage("Load properties"){
      param()
    }      
}
