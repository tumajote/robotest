pipeline {
    agent {
        docker {
            image 'ppodgorsek/robot-framework'
            args '-v /var/lib/jenkins/workspace/robotest_master/tasks:/opt/robotframework/tests:Z'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'ls -la'
            }
        }
    }
}