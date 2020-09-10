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
    steps {
    script {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv('Sonar') { // If you have configured more than one global server connection, you can specify its name
      bat "${scannerHome}/bin/sonar-scanner"
      }
      }
    }
    }
    }
}