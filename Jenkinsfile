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
           withMaven(maven : 'maven_3_6_1') {
                sh 'mvn deploy -Dversion=demo-package_P2_'${BUILD_TIMESTAMP}' -Dbuild.number=${BUILD_NUMBER}'
          }
        } 
       }
  }

}

