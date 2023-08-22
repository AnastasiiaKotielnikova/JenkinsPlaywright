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
    agent {
        docker {
            image 'node:14'  // Use an official Node.js image as an example
            args '-v /var/run/docker.sock:/var/run/docker.sock'  // Mount Docker socket
        }
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
    }
    post {
        always {
            cleanWs()  // Clean up workspace
        }
    }
}

