pipeline {
        agent any
                stages {
                         stage('One') {
                               steps {
                                       echo 'Hi, I am Biplob from BJIT Oy'
                                  }
                          }
                          stage('Two') {
                                steps {
                                         input('Do you want to Proceed?')
                                      }
                                }
                          stage('Three') {
                                 when {
                                       not {
                                             branch "master"
                                           }
                                     }
                                   steps {
                                            echo "Hello"
                                       } 
                               }
                          stage('Four') {
                                         steps {
                                                echo "Starting Testing----"
                                               }  
                                          parallel {
                                                 stage('Unit Test') {
                                                                 steps {
                                                                     echo "Running the unit test..."
                                                                       }
                                                               }
                                                  stage('Integration test') {
                                                         
                                                    steps {
                                                        echo 'Running the integration test...'
                                                      }
                                               }
                                     }    
                             }

         }
                         
}

