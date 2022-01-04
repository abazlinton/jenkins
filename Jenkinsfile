import groovy.json.JsonSlurper

def getCauseString(contentfulData, x_contentful_topic) {
  def jsonSlurper = new JsonSlurper()
  def contentfulObj = jsonSlurper.parseText(contentfulData)
  def publishReason = contentfulObj['sys']['type']
  def publishDetail = ""
  if (publishReason == 'Entry') {
    publishDetail = contentfulObj['sys']['contentType']['sys']['id']
  }
  return x_contentful_topic + " - " + publishDetail
}

pipeline {
  
  // remove me
  agent any

  // GenericTrigger section to overwrite current one
  triggers{
    GenericTrigger(
      // match token in Contentful webhook POST params
      token: 'testing123',
        
      // log whole Contentful POST body  
      printPostContent: true,
        
      // value is the JSONPath  
      genericVariables: [
        [
          key: 'contentfulData', 
          value: '$', 
          defaultValue: "",
          expressionType: 'JSONPath',   // Optional, default is JSONPath
          regexpFilter: '',             // Optional, default is empty string
          defaultValue: ''              // Optional, default is empty string
        ]
      ],
      genericHeaderVariables: [
        [key: 'X-Contentful-Topic']
      ],
        
      // uncomment below to debug Generic Webhook Trigger contributed variables  
      printContributedVariables: true,
      
      // Generic Webhook Trigger by default traverses the JSON and creates variables for each node
      causeString: "\$x_contentful_topic - \$contentfulData_sys_contentType_sys_id"
    )
  }


  // remove me
  stages {
    stage('Hello') {
      steps {
        echo 'Hello World'
      }
    }
  }
}
