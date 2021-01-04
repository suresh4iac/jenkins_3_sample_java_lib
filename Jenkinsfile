pipeline {
  agent { lable 'master' }
  stages {
    stage('Build') {
      steps {
        sh 'gradle clean build'
          junit 'build/test-results/**/TEST-*.xml'
        }
    }
    stage('deploy to staging') {
      steps {
        echo "deploying to staging"
      }
    }
    stage('deploy to production') {
      when {
        branch 'master'
      }
      steps {
        echo "deploying to production"
      }
    }
  }
}
