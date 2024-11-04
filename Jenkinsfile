pipeline {
    agent any
    parameters {
        string(name: 'CUCUMBER_TAGS', defaultValue: '', description: 'Enter Cucumber tags to run (e.g., @smoke).')
    }
    stages {
        stage('Run Cucumber Tests') {
            steps {
                script {
                    def tags = params.CUCUMBER_TAGS ?: "@smoke" // Set default if none provided
                    sh "mvn test -Dcucumber.filter.tags='${tags}'"
                }
            }
        }
    }
}
