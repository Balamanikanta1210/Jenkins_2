pipeline {
	    agent any
	

	        // Environment Variables
	        environment {
	        MAJOR = '1'
	        MINOR = '0'
	        //Orchestrator Services
	        UIPATH_ORCH_URL = "https://cloud.uipath.com/"
	        UIPATH_ORCH_LOGICAL_NAME = "eld"
	        UIPATH_ORCH_TENANT_NAME = "DefaultTenant"
	        UIPATH_ORCH_FOLDER_NAME = "Test"
	    }
	

	    stages {
	

	        // Printing Basic Information
	        stage('Preparing'){
	            steps {
	                echo "Jenkins Home ${env.JENKINS_HOME}"
	                echo "Jenkins URL ${env.JENKINS_URL}"
	                echo "Jenkins JOB Number ${env.BUILD_NUMBER}"
	                echo "Jenkins JOB Name ${env.JOB_NAME}"
	                echo "GitHub BranhName ${env.BRANCH_NAME}"
	                checkout scm
	

	            }
	        }

	  stage('installPlat') {
	            steps {
	                echo "Building..with ${WORKSPACE}"
	                UiPathInstallPlatform (
					 
					   cliNupkgPath: 'C:\\Users\\balamanikanta.krishn\\Desktop\\UiPath_CLI\\UiPath.CLI.Windows.22.10.8438.32859.zip',
					   forceInstall: true,
					   traceLevel: 'None'
					)
	            }
	        }

	         // Build Stages
	        stage('Build') {
	            steps {
	                
	                UiPathPack (
	                      outputPath: "C:\\Users\\balamanikanta.krishn\\Desktop\\UiPath_CLI",
	                      projectJsonPath: "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\ipath_Testing_SecondProject_main\\project.json",
	                      useOrchestrator: false,
			      traceLevel: 'None'
	        )
	            }
	        }
	         
	}

	}