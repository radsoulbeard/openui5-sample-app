@Library('piper-lib-os') _
//@Library('piper-landscape') __

node() {

  stage('prepare') {
      checkout scm
      setupCommonPipelineEnvironment script:this
  }

  stage('MTA build') {
      mtaBuild script: this
  }

  stage('deployment to CP') {
      neoDeploy script: this
  }
}
