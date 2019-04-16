node {

    def app

    stage('clone repository') {
        /* Lets make sure we have the repository cloned to ouy workspace*/
   
        checkout scm
     }

    stage('Builb image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
  
        app = docker docker.build("biplobcse/avro")
     }

    stage('Test image') {
         /* Ideally, we would run a test framework against our image.
          * For this example we're using a volkswagen-type approach :-) */

        app.inside {

         sh 'echo "Tests passed"'
        }
   }

    stage('Push image') {
       /* Finally, We'll push the image with two tags:
        * First, the incremental build number from Jenkins
        * Second, the 'latest' tag.
        * Pushing multiline tags is cheap, as all the layers are reused. */
       docker.withRegistry('https://registry.hub.docker.com', 'edbc6dd2-083e-449b-81fe-f7033563b3dc') {
          app.push("${env.BUILD_NUMBER}")
          app.push("latest")
    }
  }
}
