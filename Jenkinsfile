
pipeline {
    agent {label "linus"}
    stages {
        stage('Hello') {
            steps {
                echo "hello from Jenkinsfile"
            }
        }
        stage('for the fix branch') {
            when {
                branch "fix-*"
            }
            steps {
                sh '''
                    cat README.md
                '''
            }
        }
        stage('for the PR') {
            when {
                branch 'PR-*'
            }
            steps {
                echo "this only run for the PRs"
            }
        }
    }
}
