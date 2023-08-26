pipeline {
	agent any
	stages {
		stage('GIT Polling'){
		steps {
			sh 'mvn clean package'
		}
		post {
			success {
				echo "Now Archieveing"
				archiveArtifacts artifacts: '**/*.war'
			}
		}
		}
		stage('Deploy to prod'){
		steps {
			build job: 'DemoDeployPip'
		}
		}
	}
}
