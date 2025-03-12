
pipeline {
    agent {label "linus"}
    parameters {
        booleanParam(defaultValue: false, description: "Enable service?", name: "myBoolean")
    }

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
        stage("Demo") {
            steps {
                echo "booleanParam is set to: ${param.myBoolean}"
            }
        }
    }
}
