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
      script{
      def scannerhome = tool name: 'SonarScanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
      withCredentials {[string(creadentialsId: 'sonar', variable: 'sonarlogin')]} {
      sh """${scannerhome}/bin/sonar-scanner -e -Dsonar.host.url=http://localhost:9000 -Dsonar.login=${sonarlogin}"""
      }
      }
      }
}
 }