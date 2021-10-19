pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/JulianSima/Jenkins-test.git', branch: 'master', credentialsId: 'JulianSima')
        sh '''git pull https://github.com/JulianSima/Jenkins-test.git
git checkout master'''
        sh './gradlew build'
      }
    }

    stage('Test') {
      steps {
        sh './gradlew test'
      }
    }

    stage('Validate') {
      steps {
        echo 'Validated'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployed'
      }
    }

  }
}