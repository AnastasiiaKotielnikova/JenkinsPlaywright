pipeline {
  // agent { dockerfile true }
   agent { docker { 
    label 'windows'
    image 'mcr.microsoft.com/playwright:v1.37.0-jammy' 
    } }
  stages {
    // stage('install playwright') {
    //   steps {
    //     sh '''
    //       npm i -D @playwright/test
    //       npx playwright install
    //     '''
    //   }
    // }
    // stage('help') {
    //   steps {
    //     sh 'npx playwright test --help'
    //   }
    // }
    stage('test'){
        steps{
           sh 'ci'
            sh 'npx playwright test'
            // sh '''
            // npx playwright test --list
            // npx playwright test
            // '''
        }
    }
  }
}