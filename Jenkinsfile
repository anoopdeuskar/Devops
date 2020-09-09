def readfile
def var1
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
       stage('properties') {
        steps {
		 readfile = readProperties file:'build.properties'
         var1 = readfile['project']
         echo "The Application name is' - ${var1}"
       }
       }
 }
}