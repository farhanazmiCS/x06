pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                // Replace the URL with your Git repository URL
                git url: 'https://github.com/farhanazmiCS/x06.git', branch: 'master'
            }
        }

        stage('OWASP DependencyCheck') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
            }
        }
    }
    post {
        success {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}