import groovy.json.JsonSlurper

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
          key: 'contentChange', 
          value: '$.sys.contentType.sys.id', 
          defaultValue: "",
          expressionType: 'JSONPath',   // Optional, default is JSONPath
          regexpFilter: '',             // Optional, default is empty string
          defaultValue: ''              // Optional, default is empty string
        ],
        [
          key: 'contentTypeChange', 
          value: '$.sys.id', 
          defaultValue: "",
          expressionType: 'JSONPath',   // Optional, default is JSONPath
          regexpFilter: '',             // Optional, default is empty string
          defaultValue: ''              // Optional, default is empty string
        ],
        [
          key: 'assetChange', 
          value: '$.fields.title.en-US', 
          defaultValue: "",
          expressionType: 'JSONPath',   // Optional, default is JSONPath
          regexpFilter: '',             // Optional, default is empty string
          defaultValue: ''              // Optional, default is empty string
        ],
        [
          key: 'updatedAt', 
          value: '$.sys.updatedAt',
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
      causeString: "\$x_contentful_topic - \$contentChange\$contentTypeChange\$assetChange - \$updatedAt"
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
