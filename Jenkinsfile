pipeline {
	agent any
	stages {
		stage(build) {
			steps {
				echo 'Building'
        sh 'ls -l'
        sh 'id'
        sh 'who am i'
        sh 'docker ps'
        sh 'docker build -t enjoydevops:${BRANCH_NAME}-${BUILD_ID} .'
			}
		}
		stage(test) {
			steps {
				echo 'Testing'
        sh 'ls -l'
        sh 'id'
        sh 'who am i'
        sh 'docker ps'
				sh 'docker images'
			}
		}
		stage(deploy) {
			steps {
				echo 'Deploying'
			}
		}
	}
}
