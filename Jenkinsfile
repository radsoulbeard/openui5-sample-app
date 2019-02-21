@Library('piper-lib-ye') _

node() {

  stage('prepare') {
      checkout scm
      setupCommonPipelineEnvironment script:this
  }

  stage('build') {
      npmExecute script: this, dockerImage: 'node:8-stretch', npmCommand: 'run build'
  }
}
