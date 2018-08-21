pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        checkout([$class: 'GitSCM',
                  branches: [[name: '*/master']],
                  doGenerateSubmoduleConfigurations: false,
                  extensions: [[$class: 'PathRestriction',
                                excludedRegions: 'src/test',
                                includedRegions: '']],
                  submoduleCfg: [],
                  userRemoteConfigs: [[credentialsId: 'GitHub', url: 'https://github.com/ChristianLangmann/spring-petclinic.git']]])
      }
    }
    stage('build') {
      sh 'ls src/'
    }
  }
}