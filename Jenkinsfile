pipeline{
 agent any
 stages {
      stage ('Greet'){
      steps {
          echo "Hello"
      }
      }
       stage('Code Coverage') {
        steps {
          echo 'We are doing code coverage test now'
       }
       }
       stage('Build') {
        steps {
        script{
		 properties = readProperties file:'build.properties'
         echo "The Application name is - ${properties.project}"
         }
       }
       }
       stage('version') {
        steps {
        script{
         echo "The Application version is - ${properties.version}"
         }
       }
       }
 }
}