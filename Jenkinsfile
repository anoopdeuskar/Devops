pipeline{
 agent any
 stages {
      stage ('Read'){
      steps {
          echo "Hello"
      }
      }
       stage('Code Coverage') {
        steps {
          echo 'We are doing code coverage test now'
       }
       }
       stage('prepare') {
        steps {
        script{
		 properties = readProperties file:'build.properties'
         echo "The Application name is - ${properties.project}"
         }
       }
       }
 }
}