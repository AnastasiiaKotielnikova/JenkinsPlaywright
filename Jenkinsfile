pipeline {
   agent {docker {
    image 'mcr.microsoft.com/playwright:v1.37.0-focal'
   }}
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
    stage('reports') {
    steps {
    script {
            allure([
                    includeProperties: false,
                    jdk: '',
                    properties: [],
                    reportBuildPolicy: 'ALWAYS',
                    results: [[path: 'target/allure-results']]
            ])
    }
    }
}
  }
}

