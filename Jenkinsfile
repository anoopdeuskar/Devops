pipeline {
         agent any
         stages {
                 stage('checkout') {
                 steps {
                     echo 'Hi, this is Anoop'
					 echo 'We are now checking out code from GIT'
					 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/anoopdeuskar/Devops.git']]])
                 }
                 }
                 stage('Build') {
                 steps {
                    input('Do you want to proceed?')
                 }
                 }
         }
         }
