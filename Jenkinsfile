pipeline {
    agent {
        label 'ansible'
    }
    stages {
        stage (first) {
            steps {
                sh 'echo "molecule"'
            }
        }
        stage (second) {
            steps {
                sh "molecule test"
            }
        }
    }
}
