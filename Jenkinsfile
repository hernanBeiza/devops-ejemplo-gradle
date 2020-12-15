pipeline {
	agent any

	stages {
		stage('Pipeline') {
			steps {
		      	script {
				    stage('build & test') {
				    	//Usar el gradlewrapper, incluido en el repo
				    	sh './gradlew clean build'
				    }
				    stage('sonar') {
				    	//Nombre en SonarQubeScanner en AdminJenkins/ConfigureTools/SonarQubeScanner
				    	def scannerHome = tool 'sonar-scanner';
				    	//Nombre en AdminJenkins/Configuración Global/SonarQube Servers
					    withSonarQubeEnv('sonar') { 
					    	// If you have configured more than one global server connection, you can specify its name
							sh "{scannerHome}/bin/sonar-scanner -Dsonar.projectKey=ejemplo-gradle -Dsonar.java.binaries=build "							
						}
				    }
				    stage('run') {
				    	//sh './gradle build'

				    }
				    stage('rest') {
				    	//sh './gradle build'

				    }
				    stage('nexus') {

				    }
	      		}
			}
    	}
	}

}
