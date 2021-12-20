pipeline {
    agent any

    triggers{
        GenericTrigger(
          token: 'testing123',
          printPostContent: true,
            genericVariables: [
                [key: 'data', value: '$..*', defaultValue: "{}"]
            ]
        )
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo '$data'
            }
        }
    }
}
