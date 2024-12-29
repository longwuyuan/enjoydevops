pipeline {
	agent any
	stages {
		stage(build) {
			steps {
				echo 'Building'
        sh 'ls -l'
        script {
            kubernetes.image().withName("enjoydevops").build().fromPath(".")
          }
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
