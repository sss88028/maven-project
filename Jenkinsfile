pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        build 'PackageMaven'
      }
    }

    stage('DeployToStaging') {
      parallel {
        stage('DeployToStaging') {
          steps {
            build 'DeployToStaging'
          }
        }

        stage('StaticAnalysis') {
          steps {
            build 'StaticAnalysis'
          }
        }

      }
    }

  }
}