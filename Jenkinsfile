pipeline {
    agent {
        docker {
            image 'ppodgorsek/robot-framework'
            args '-v /var/lib/jenkins/workspace/robotest_master/tasks:/opt/robotframework/tests:Z -v data:/opt/robotframework/reports:Z'
        }
    }
    stages {
        stage('Save logs') {
            steps {
    step(
    [
    $class : 'RobotPublisher',
    outputPath : outputDirectory,
    outputFileName : "*.xml",
    disableArchiveOutput : false,
    passThreshold : 100,
    unstableThreshold: 95.0,
    otherFiles : "*.png",

    ]
    )            }
        }
    }
}