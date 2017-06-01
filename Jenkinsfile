pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Beginning....."
                sh "ls"
                sh "pwd"
                sh 'mvn -Dmaven.test.failure.ignore clean compile package'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
            sh "java -cp target/JenkinsMaven-0.0.1-SNAPSHOT.jar com.cme.jenkins.JenkinsMaven.App"
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
