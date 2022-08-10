pipeline {

    agent any

    stages {

        stage ('Initialization') {
            steps {
                sh 'echo "add testting: Starting the build..."'
            }
        }

	stage ('Build') {
            steps {
                sh 'npm install'
	    }
        }

	stage ('NPM Audit Analysis') {
            steps {
                sh '/bitnami/jenkins/home/npm-audit.sh'
		sh 'cat /bitnami/jenkins/home/reports/npm-audit-report'
            }
        }

	stage ('Lint Analysis with Jshint') {
	    steps {
		sh '/bitnami/jenkins/home/jshint-script.sh'
		sh 'cat /bitnami/jenkins/home/reports/jshint-report'
	    }
	}
    }

}
