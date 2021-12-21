pipeline {
  agent any

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
        
      // uncomment below to debug Generic Webhook Trigger contributed variables  
      // printContributedVariables: true,
      
      // Generic Webhook Trigger by default traverses the JSON and creates variables for each node
      causeString: 'Contentful: $contentfulData_sys_contentType_sys_id $contentfulData_sys_updatedAt'
    )
  }
  stages {
    stage('Hello') {
      steps {
        echo 'Hello World'
      }
    }
  }
}
