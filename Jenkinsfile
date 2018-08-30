pipeline {
  agent any
  stages {
    stage('Stage1') {
      parallel {
        stage('Build') {
          steps {
            addBadge(icon: 'Build ', text: 'Build CloudN')
          }
        }
        stage('cloudn') {
          steps {
            build(job: 'build-cloudn', propagate: true, wait: true, quietPeriod: 10)
          }
        }
      }
    }
    stage('Stage2') {
      steps {
        addInfoBadge 'Transit Scaling - Stage1'
      }
    }
    stage('Stage3') {
      steps {
        addInfoBadge 'Transit Scaling - Stage2'
      }
    }
    stage('Stage4') {
      steps {
        addInfoBadge 'Transit Scaling - Stage3'
      }
    }
    stage('Stage5') {
      steps {
        addInfoBadge 'Stage5'
      }
    }
    stage('Stage6') {
      steps {
        echo 'stage6'
      }
    }
  }
}