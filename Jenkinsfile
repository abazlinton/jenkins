pipeline {
    agent any

    triggers{
        GenericTrigger(
          token: 'testing123'
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
