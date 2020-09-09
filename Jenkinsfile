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
		 def readfile = readProperties file: 'build.properties'
         def var1= readfile['project']
         echo "The Application name is' - ${readfile['project']}"
       }
       }
 }
}