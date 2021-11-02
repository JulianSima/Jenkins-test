pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/JulianSima/Jenkins-test.git', branch: 'master', credentialsId: 'JulianSima')
        sh '''git pull https://github.com/JulianSima/Jenkins-test.git
git checkout master'''
        sh './gradlew :spotlessApply'
        sh './gradlew build'
      }
    }

    stage('Test') {
      steps {
        sh './gradlew test'
      }
    }

    stage('Analyze') {
      steps {
        sh './gradlew sonarqube -Dsonar.host.url=localhost:9000'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployed'
      }
    }

  }
}