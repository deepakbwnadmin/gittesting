pipeline {



agent any
    // Build stages:
    stages {
			stage('Copy contents') {
            steps {
		sh "rm -rf /tmp/jenkins/*"
		sleep 10
                sh "cp -rf /tmp/pipelinetest /tmp/jenkins"
            		}
    		}
	}

post {
        cleanup {
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
    }

}
