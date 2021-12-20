pipeline {
    agent any

    triggers{
        GenericTrigger(
          token: 'testing123',
          printPostContent: true,
            genericVariables: [
                [key: 'data', value: '$..*']
            ]
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
