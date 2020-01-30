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
    sh 'echo "jotain"'
    )
        }
      }

    }
  }
