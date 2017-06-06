pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Beginning....."
                sh "ls"
                sh "pwd"
                sh 'mvn clean compile package deploy'
            }
        }
    }
    post {
        always {
            echo 'In always block---------->> This will always run'
        }
        success {
            echo 'In success block--------->> This will run only if successful'
            sh "java -cp target/JenkinsMaven-0.0.1-SNAPSHOT.jar com.cme.jenkins.JenkinsMaven.App"
        }
        failure {
            echo 'In failure block--------->> This will run only if failed'
        }
        unstable {
            echo 'In unstable block-------->> This will run only if the run was marked as unstable'
        }
        changed {
            echo 'In Changed Block------->> This will run only if the state of the Pipeline has changed For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
