pipeline {
         agent any
         stages {
         
				 stage('Read') {
                 steps {
					def readfile = readProperties file: 'build.properties'
					echo "The Application name is' - ${readfile['project']}"
                 }
                 }
                 stage('Build') {
                 steps {
                     echo 'Hi, this is Anoop'
					 echo 'We are now checking out code from GIT'
					 input('Do you want to proceed?')
                 }
                 }
                 stage('Code Coverage') {
                 steps {
                    echo 'We are doing code coverage test now'
                 }
                 }
				 }
         }  
