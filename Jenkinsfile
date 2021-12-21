pipeline {
    agent any

    parameters {
        string(name: 'contentfulData_environment_id', defaultValue: 'no Webhook', description: 'Ensure contentfulData_environment_id is present even if build manually triggered')  
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
