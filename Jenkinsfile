pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build demo app'
        sh 'sh run_build_scrip.sh'
      }
    }

    stage('linux test') {
      parallel {
        stage('linux test') {
          steps {
            echo 'run linux test'
            sh 'sh run_linux_test.sh'
          }
        }

        stage('Windows test') {
          steps {
            echo 'windows test'
          }
        }

      }
    }

    stage('deploy staging') {
      steps {
        echo 'deploy to staging'
        input 'Click to deply to production'
      }
    }

    stage('deploy production') {
      steps {
        echo 'deploy to production'
      }
    }

  }
}