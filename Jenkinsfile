pipeline {
  node {
    checkout scm
    def dockerfile = 'Dockerfile'
    def customImage = docker.build("docker-jenkins-pipeline:${env.BUILD_ID}", "-f ${dockerfile} .")
}
  stages {
    stage('install playwright') {
      steps {
        sh '''
          npm i -D @playwright/test
          npx playwright install
        '''
      }
    }
    stage('help') {
      steps {
        sh 'npx playwright test --help'
      }
    }
    stage('test'){
        steps{
            sh '''
            npx playwright test --list
            npx playwright test
            '''
        }
    }
  }
}