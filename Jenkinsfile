pipeline {
    agent any
    stages {
       stage ('Build') {
           steps {
           sh 'echo "This is my first stage in jenkins in which I have built the application"'
                 }
                       }
       stage ('Test') {
             steps {
           sh 'echo "This is my second stage in jenkins in which I have tested the application"'
                   } 
                      }
        stage ('Deploy') {
             steps {
            sh  'echo "This is my third stage in jenkins in which I deploy the application"'
                   }
                         }
           }
}
