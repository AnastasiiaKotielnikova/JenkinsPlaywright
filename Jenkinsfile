pipeline {
  agent { 
    docker { 
      image 'mcr.microsoft.com/playwright:v1.37.0-jammy'
    } 
  }
  stages {
    stage('install playwright') {
      steps {
        ssh '''
          npm i -D @playwright/test
          npx playwright install
        '''
      }
    }
    stage('help') {
      steps {
        ssh 'npx playwright test --help'
      }
    }
    stage('test'){
        steps{
            ssh '''
            npx playwright test --list
            npx playwright test
            '''
        }
    }
  }
}