pipeline {
	agent any
	stages {
		stage(build) {
			steps {
				echo 'Building'
        sh 'cd src'
        sh 'ls -l'
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
