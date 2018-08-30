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
      parallel {
        stage('Stage2') {
          steps {
            addInfoBadge 'Transit Scaling - Stage1'
          }
        }
        stage('build-transit-framework') {
          steps {
            build(job: 'colby-build-transit-framework', propagate: true, wait: true, quietPeriod: 20)
          }
        }
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
    stage('Stage7') {
      parallel {
        stage('Stage7') {
          steps {
            addBadge(icon: 'Stage7', text: 'Stage7')
          }
        }
        stage('colby-build-transit-framework-DESTROY') {
          steps {
            build(job: 'colby-build-transit-framework-DESTROY', propagate: true, quietPeriod: 20, wait: true)
          }
        }
      }
    }
  }
}