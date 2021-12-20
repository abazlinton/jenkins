pipeline {
    agent any

    triggers{
        GenericTrigger(
          token: 'testing123',
          printPostContent: true,
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
