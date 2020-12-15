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
							def ejecucionMaven = load 'maven.groovy'
							ejecucionMaven.call()
			    		} else {
							def ejecucionGradle = load 'gradle.groovy'
							ejecucionGradle.call()
			    		}
				    }
	      		}
			}
    	}
	}

}