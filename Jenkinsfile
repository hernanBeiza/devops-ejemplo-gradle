pipeline {
	agent any
	/*
	parameters {
    	choice(
	        name: 'paramHerramienta',
	        choices: "maven\ngradle",
	        description: 'Parámetro que determinará si se ejecuta maven.groovy o gradle.groovy'
        )
	}
	*/
	stages {
		stage('Pipeline') {
			steps {
		      	script {
				    stage('iniciar') {
				    	echo "iniciar"
				    	String paramHerramienta = params.paramHerramienta;
				    	echo "paramHerramienta ${paramHerramienta}";
				    	if(paramHerramienta=="maven"){
				    		env.BUILD_TOOL="MAVEN";
							def ejecucionMaven = load 'maven.groovy'
							ejecucionMaven.call()
			    		} else {
				    		env.BUILD_TOOL="GRADLE";
							def ejecucionGradle = load 'gradle.groovy'
							ejecucionGradle.call()
			    		}
				    }
	      		}
			}
    	}
	}
    //Manejar si el pipeline fue exitoso o fallido
    post {
        success {
        	echo "Ejecución exitosa [${env.CHANGE_AUTHOR_DISPLAY_NAME}][${env.JOB_NAME}][${env.BUILD_TOOL}]";
            slackSend channel: 'D01E5ED8TK2', color: 'good', message: 'Ejecución exitosa [${env.CHANGE_AUTHOR_DISPLAY_NAME}][${env.JOB_NAME}][${env.BUILD_TOOL}]', teamDomain: 'dipdevopsusach2020', tokenCredentialId: 'jenkins-slack'
        }
        failure {
	    	echo "Ejecución fallida [${env.CHANGE_AUTHOR_DISPLAY_NAME}][${env.JOB_NAME}][${env.BUILD_TOOL}] en stage [${env.STAGE_NAME}]";
            slackSend channel: 'D01E5ED8TK2', color: 'danger', message: 'Ejecución fallida [${env.CHANGE_AUTHOR_DISPLAY_NAME}][${env.JOB_NAME}][${env.BUILD_TOOL}] en stage [${env.STAGE_NAME}]', teamDomain: 'dipdevopsusach2020', tokenCredentialId: 'jenkins-slack'
        }
    }

}