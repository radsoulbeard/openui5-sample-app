@Library('piper-lib-os') _

node() {

  stage('prepare') {
		  deleteDir()
      checkout scm
      setupCommonPipelineEnvironment script:this
  }

  stage('build') {
      mtaBuild script: this, dockerImage: 'ppiper/mta-archive-builder', buildTarget: 'CF'
  }

  stage('deploy') {
      cloudFoundryDeploy script: this, dockerImage: 'ppiper/cf-cli'
  }
}
