pipeline {
	agent any
	environment {
		IMAGE_TAG = getShortSHA()
	}
	stages {
		stage(build) {
			steps {
				echo 'Building'
        sh 'ls -l'
        sh 'id'
        sh 'who am i'
        sh 'docker ps'
        sh 'docker build -t enjoydevops:${BRANCH_NAME}-${IMAGE_TAG} .'
        sh 'docker tag  enjoydevops:${BRANCH_NAME}-${IMAGE_TAG} enjoydevops:${BRANCH_NAME}-${BUILD_ID}'
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
				sh 'which kubectl'
				sh 'kubectl get ns'
				sh '$HOME/go/bin/kind load docker-image  enjoydevops:${BRANCH_NAME}-${IMAGE_TAG}'
				sh 'kubectl set image deployments enjoydevops nginx="docker.io/library/enjoydevops:${BRANCH_NAME}-${IMAGE_TAG}"'
			}
		}
	}
}

def getShortSHA(){
    def commitHash = sh label: '', returnStdout: true, script: 'git rev-parse --short HEAD'
    return commitHash
}
