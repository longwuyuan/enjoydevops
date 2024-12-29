pipeline {
	agent any
	stages {
		stage(build) {
			steps {
				echo 'Building'
        sh 'ls -l'
        sh 'docker build -t enjoydevops .'
			}
		}
		stage(test) {
			steps {
				echo 'Testing'
			}
		}
		stage(deploy) {
			steps {
				echo 'Deploying'
			}
		}
	}
}
