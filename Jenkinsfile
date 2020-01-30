pipeline {
  agent {
    docker {
      image 'ppodgorsek/robot-framework'
      args '''--rm
-v data:/opt/robotframework/reports:Z
-v /var/lib/jenkins/workspace/robotest/tasks:/opt/robotframework/tests:Z'''
    }

  }
  stages {
    stage('Result') {
      steps {
        step(
    [
    $class : \'RobotPublisher\',
    outputPath : outputDirectory,
    outputFileName : "*.xml",
    disableArchiveOutput : false,
    passThreshold : 100,
    unstableThreshold: 95.0,
    otherFiles : "*.png",
    ]
        }
      }

    }
  }
