pipeline {



agent any
    // Build stages:
    stages {
			stage('Copy contents') {
            steps {
		sh "rm -rf /tmp/jenkins/*"
		sleep 20
                sh "cp -rf /tmp/pipelinetest /tmp/jenkins"
            		}
    		}
	}
}
