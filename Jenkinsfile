// pipeline {
//    agent { dockerfile true }
//   stages {
//     stage('install playwright') {
//       steps {
//         sh '''
//           npm i -D @playwright/test
//           npx playwright install
//         '''
//       }
//     }
//     stage('help') {
//       steps {
//         sh 'npx playwright test --help'
//       }
//     }
//     stage('test'){
//         steps{
//             sh '''
//             npx playwright test --list
//             npx playwright test
//             '''
//         }
//     }
//   }
// }


pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from the repository
                checkout scm
            }
        }
        
        stage('Install and Test') {
            steps {
                script {
                    // Install dependencies and run Playwright tests
                    sh 'npm install'
                    sh 'npm test'
                }
            }
        }
    }
}