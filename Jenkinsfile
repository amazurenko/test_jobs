import groovy.json.JsonSlurper
def inputFile = new File("properties")
InputJSON = new JsonSlurper().parseText(inputFile.text)
node{
    stage("Preparation"){
      checkout scm
    }
    stage("Load properties"){
      InputJSON.each{ println it }
    }      
}
