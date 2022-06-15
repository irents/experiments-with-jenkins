pipeline {
    agent any
    
    stages {
          stage('Test on linux') {
               steps {
                   sh 'npm install'
                   sh 'npm run test-e2e'
               }

               post {
                   always {
                       junit keepLongStdio: true, 
                             testDataPublishers: [[$class: 'TestCafePublisher']], 
                             testResults: '*.xml'
                   }
               }
         }
    }
}
