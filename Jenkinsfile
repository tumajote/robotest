pipeline {
  agent {
    docker {
      image 'ppodgorsek/robot-framework'
      args '''--rm
-v var/lib/jenkins/workspace/robotest_master/tasks/:/opt/robotframework/tests:Z'''
    }

  }
  stages {
    stage('Result') {
      steps {
            step(
    [
    $class : 'RobotPublisher',
    outputPath : /opt/robotframework/reports,
    outputFileName : "*.xml",
    disableArchiveOutput : false,
    passThreshold : 100,
    unstableThreshold: 95.0,
    otherFiles : "*.png",

    ]
    )
        }
      }

    }
  }
