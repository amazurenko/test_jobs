import groovy.json.JsonSlurper

@NonCPS
def param(){
    def inputFile = new File("./properties")
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
