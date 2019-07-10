pipeline {
  agent any
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/HarukiHashimoto/kou-lab', branch: 'master')
      }
    }
    stage('') {
      steps {
        sh 'npm run generate'
      }
    }
  }
}