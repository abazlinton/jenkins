pipeline {
    agent any
 
    triggers{
        GenericTrigger(
          token: 'testing123',
          printPostContent: true,
          genericVariables: [
              [key: 'contentfulData', value: '$.contentfulData', defaultValue: ""]
          ],
          printContributedVariables: true,
          causeString: 'Contentful: $contentfulData_sys_contentType_sys_id'
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
