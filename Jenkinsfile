@Library('piper-library-os') _
@Library('piper-landscape') __

node() {

  stage('prepare') {

      checkout scm

      setupCommonPipelineEnvironment script:this

      //checkChangeInDevelopment script: this
  }

  stage('build') {
      mtaBuild script: this
  }

  stage('neoDeploy') {
      neoDeploy script: this
  }

}
