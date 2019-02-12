@Library('piper-lib-os') _

node() {

  stage('prepare') {
		  deleteDir()
      checkout scm
      setupCommonPipelineEnvironment script:this
  }

  stage('build') {
      mtaBuild script: this, dockerImage: 'ppiper/mta-archive-builder'
  }

  stage('neoDeploy') {
      neoDeploy script: this
  }
}
