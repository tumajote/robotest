pipeline {
  agent any
  stages {
    stage('setup') {
      steps {
          sh "mkdir data"
      }
    }
    stage('2') {
      steps {
          sh "docker ps"
      }
    }
    stage('3') {
      steps {
          sh "cat /etc/group"
      }
    }
    stage('build and run') {
      steps {
        sh "docker run --rm \
        -v /var/jenkins_home/workspace/robotest_master/data:/opt/robotframework/reports:Z \
        -v /var/jenkins_home/workspace/robotest_master/tasks:/opt/robotframework/tests:Z \
        ppodgorsek/robot-framework"
      }
    }
    stage('save robot output') {
      steps {
step(
    [
    $class : 'RobotPublisher',
    outputPath : '/var/jenkins_home/workspace/robotest_master/data',
    outputFileName : "*.xml",
    disableArchiveOutput : false,
    passThreshold : 100,
    unstableThreshold: 95.0,
    otherFiles : "*.png",

    ]
    )        }
    }

    stage('Input to database') {
      steps {

             }
    }

    stage('close') {
      steps {
        sh "rm -r data"
        sh "docker container prune --force"
      }
    }

  }
}
