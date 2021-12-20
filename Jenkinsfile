pipeline {
    agent any

    triggers{
        GenericTrigger(
          token: 'testing123',
          printPostContent: true,
            genericVariables: [
                [key: 'data', value: '$.data', defaultValue: "{}"]
            ]
        )
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh "echo $data"
            }
        }
    }
}
