pipeline {
    agent any
    
    stages {
        stage ('Compile Stage') {
         
          steps {
            withMaven(maven : 'maven_3_6_1') {
               sh 'mvn clean compile'
              
             }
           }
        }
      
    
        stage ('Testing Stage'){
           steps {
             withMaven(maven : 'maven_3_6_1') {
                sh 'mvn test'
          }
         }
        }

    stage ('Deploy Stage') {
       steps {
           sh 'echo hello'
        } 
       }
    stage('CleanWorkspace') {
            steps {
                cleanWs()
            } 
     } 
  }

}
