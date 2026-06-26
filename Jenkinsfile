pipeline {
    agent any
    parameters {
        string(name: 'IMAGE_TAG', defaultValue: 'latest', description: 'Docker image tag to deploy')
    }
    stages {
        stage('Deploy with Helm') {
            steps {
                script {
                    sh """
					    pwd
						cp -R helm/* .
						ls -ltr
						pwd
                        helm upgrade --install petclinic-app petclinic --set image.tag=${params.IMAGE_TAG}
                    """
                }
            }
        }
    }
}
