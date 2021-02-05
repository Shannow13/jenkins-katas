pipeline {
  agent {
    docker {
      image 'gradle:jdk11'
    }

  }
  stages {
    stage('Parallel build') {
      parallel {
        stage('Say Hello') {
          agent {
            docker {
              image 'gradle:jdk11'
            }

          }
          steps {
            sh 'echo "HelloWorld"'
          }
        }

        stage('Build App') {
          agent {
            docker {
              image 'gradle:jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}