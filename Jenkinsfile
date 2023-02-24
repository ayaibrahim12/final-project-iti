pipeline {
    agent { label 'agent' }
    stages {
        stage('build') {
            steps {
                script {
                    sh   """
                        docker build -t gcr.io/aya-ibrahim79632/final_project .
                        docker push gcr.io/aya-ibrahim79632/final_project
                    """
                }
            }
        }
        stage('deploy') {
            steps {
                script {
                    sh    """
                        kubectl apply -f k8s-files
                    """
                }
            }
        }
    }
}
