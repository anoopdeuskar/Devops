pipeline{
 agent any
 stages {
       stage('property_check') {
       steps {
          echo 'We are doing property checks now'
       }
       }
      stage ('Build'){
      steps {
          echo "Code is now being Build"
      }
      }
      stage('Test') {
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
      stage('SonarQube_analysis') {
      def scannerhome = tool ('SonarScanner')
      withSonarQubeEnv {'Sonar'} {
      sh """${scannerhome}/bin/sonar-scanner """
      }
  }
}
 }