pipeline {
    agent any

    triggers{
        GenericTrigger(
          token: 'testing123',
          printPostContent: true,
            genericVariables: [
                [key: 'contentfulData', value: '$.contentfulData', defaultValue: "{}"]
            ]
          printContributedVariables: true
        )
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh "echo $contentfulData"
            }
        }
    }
}
