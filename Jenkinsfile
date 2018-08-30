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
            build(job: 'Build CloudN', propagate: true, wait: true, quietPeriod: 10)
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
  }
}