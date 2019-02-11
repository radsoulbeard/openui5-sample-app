@Library('piper-lib-os') _

node() {

  stage('prepare') {

      checkout scm

      setupCommonPipelineEnvironment script:this

      //checkChangeInDevelopment script: this
  }

  stage('build') {
			sh 'mkdir -p dist'
      mtaBuild script: this, dockerImage: 'ppiper/mta-archive-builder'
  }

  stage('neoDeploy') {
      neoDeploy script: this
  }

}
