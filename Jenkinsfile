pipeline {
  agent any
  stages {
    stage('build and run') {
      steps {
        sh "docker run --rm \
        -v data:/opt/robotframework/reports:Z \
        -v /var/jenkins_home/workspace/RoboDemo_master/tasks:/opt/robotframework/tests:Z \
        ppodgorsek/robot-framework"
      }
    }
    stage('save') {
      steps {
step(
    [
    $class : 'RobotPublisher',
    outputPath : '/var/lib/docker/volumes/data/_data',
    outputFileName : "*.xml",
    disableArchiveOutput : false,
    passThreshold : 100,
    unstableThreshold: 95.0,
    otherFiles : "*.png",

    ]
    )        }
    }

    stage('close') {
      steps {
        sh "docker container prune --force"
        sh "docker volume prune --force"
      }
    }

  }
}