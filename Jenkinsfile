pipeline {
    agent any
 
    triggers{
        GenericTrigger(
          token: 'testing123',
          printPostContent: true,
          genericVariables: [
              [key: 'contentfulData', value: '$', defaultValue: ""]
          ],
          printContributedVariables: true,
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
