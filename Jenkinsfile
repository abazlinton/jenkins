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
          // Content Type (Model) of the changed Content
          key: 'contentType', 
          value: '$.sys.contentType.sys.id', 
          defaultValue: '',
          expressionType: 'JSONPath',   // Optional, default is JSONPath
          regexpFilter: '',             // Optional, default is empty string
          // defaultValue: ''              // Optional, default is empty string
        ],
        [
          // Way of identifying a changed Asset (Media)
          key: 'title', 
          value: '$.fields.title.en-US', 
          // defaultValue: '',
        ],
        [
          key: 'updatedAt', 
          value: '$.sys.updatedAt',
          // defaultValue: '',
        ]
      ],
      genericHeaderVariables: [
        // e.g. ContentManagement.Entry.publish
        // e.g. ContentManagement.Entry.unpublish
        // Appears to be only way of finding the 'kind' of change
        [key: 'X-Contentful-Topic']
      ],
        
      // uncomment below to debug Generic Webhook Trigger contributed variables  
      printContributedVariables: true,
      
      // Generic Webhook Trigger by default traverses the JSON and creates variables for each node
      causeString: '$x_contentful_topic - $contentType$title - $updatedAt'
    )
  }


  // remove me
  stages {
    stage('Hello') {
      steps {
        echo x_contentful_topic
      }
    }
  }
}
