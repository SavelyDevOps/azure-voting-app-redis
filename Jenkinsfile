pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Verify User') {
         steps {
            sh 'echo ${USER}'
         }
      }
      stage('Docker Build') {
         steps {
            sh 'docker images -a'
            sh 'echo ${USER}'
            sh '''
               cd azure-vote/
               docker images -a
               docker build -t jenkins-pipeline .
               docker images -a
               cd ..
            '''
         }
      }
   }
}
