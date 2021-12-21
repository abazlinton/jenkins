pipeline {
    agent any

    parameters {
        string('contentfulData_environment_id', 'no Webhook', 'Make sure this variable is present even if build manually triggered')  
    }
    
    triggers{
        GenericTrigger(
          token: 'testing123',
          printPostContent: true,
          genericVariables: [
              [key: 'contentfulData', value: '$.contentfulData', defaultValue: ""]
          ],
          printContributedVariables: true,
          causeString: 'Contentful: $contentfulData.environment.id'
        )
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo contentfulData_environment_id
            }
        }
    }
}
