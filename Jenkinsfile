pipeline {
    agent any
    tools {
        maven 'MVN1'
          }
    stages {
       stage ('Build Jar') {
           steps {
           sh 'echo "Building the jar file"'
           sh 'mvn build'   
                 }
                       }
       stage ('Build Image') {
             steps {
           sh 'echo "Building Docker Image"'
           withCredentials([usernamePassword(credentialsId: 'mydockerhub', passwordVariable: 'PASS', usernameVariable: 'USER')])
           sh 'docker build -t ahesmat/meddy-repo:jma-2.0 .'
           sh "echo $PASS | docker login -u $USR --password-stdin"
           sh 'docker push ahesmat/meddy-repo:jma-2.0'      
                 
                   } 
                      }
        stage ('Deploy') {
             steps {
            sh  'echo "This is my third stage in jenkins in which I deploy the application"'
                   }
                         }
           }
}
