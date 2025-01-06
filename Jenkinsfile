pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh 'echo "distributionBase=GRADLE_USER_HOME" > ./gradle/wrapper/gradle-wrapper.properties'
                sh 'echo "distributionPath=wrapper/dists" >> ./gradle/wrapper/gradle-wrapper.properties'
                sh 'echo "distributionUrl=https\\://services.gradle.org/distributions/gradle-8.12-bin.zip" >> ./gradle/wrapper/gradle-wrapper.properties'
                sh 'echo "zipStoreBase=GRADLE_USER_HOME" >> ./gradle/wrapper/gradle-wrapper.properties'
                sh 'echo "zipStorePath=wrapper/dists" >> ./gradle/wrapper/gradle-wrapper.properties'
                sh 'cat ./gradle/wrapper/gradle-wrapper.properties'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
    }
}
