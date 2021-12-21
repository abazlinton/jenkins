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
          causeString: 'Contentful: $Imadethisup $contentfulData_sys_updatedAt'
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
