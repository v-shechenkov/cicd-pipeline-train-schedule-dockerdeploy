pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                sh 'cat /var/lib/jenkins/workspace/train-schedule_master/build.gradle]'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
    }
}
